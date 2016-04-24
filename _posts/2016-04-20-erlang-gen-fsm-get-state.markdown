---
layout: post
title:  "Erlang gen_fsm: check current status"
date:   2016-04-20 05:58:21 +0200
categories: erlang eunit
---

```erlang
% Client

%%% Api

introspection_statename(StateName) ->
    gen_fsm:sync_send_all_state_event(StateName,which_statename).

%%% gen_fsm callbacks

handle_sync_event(which_statename, _From, StateName, LoopData) ->
    {reply, StateName, StateName, LoopData};

% Test

valid_initial_status(Pid) ->
    [?_assertEqual(idle, trade_fsm:introspection_statename(Pid))].
```

Cleaner way:

```erlang
% Test
{CurrentStateName, _CurrentStateData} = sys:get_state(Pid),
?assertEqual(idle, CurrentStateName)
```

Comparing implementations from `eunit_fsm`:

{% highlight ruby linenos %}
%% Bad

translateCmd(Pid, {state,is,X}) ->
    case getStateName(Pid) of
        X -> ok;
        V -> erlang:error({statename_match_failed,
                           [{module, ?MODULE},
                            {line, ?LINE},
                            {expected, X},
                            {value, V}]})
    end.

getStateName(Pid) ->
    {CurrentStateName, _CurrentStateData} = sys:get_state(Pid),
    CurrentStateName.

%% Good

translateCmd(Pid, {state,is,X}) ->
    {CurrentStateName, _CurrentStateData} = sys:get_state(Pid),
    ?assertEqual(X, CurrentStateName).
{% endhighlight %}

**Module sys**

# get_state(Name) -> State

# get_state(Name, Timeout) -> State

These functions are intended only to help with debugging. They are provided for
convenience, allowing developers to avoid having to create their own state
extraction functions and also avoid having to interactively extract state from
the return values of get_status/1 or get_status/2 while debugging.

The value of State varies for different types of processes. For a gen_server
process, the returned State is simply the callback module's state. For a
gen_fsm process, State is the tuple {CurrentStateName, CurrentStateData}. For a
gen_event process, State a list of tuples, where each tuple corresponds to an
event handler registered in the process and contains {Module, Id,
HandlerState}, where Module is the event handler's module name, Id is the
handler's ID (which is the value false if it was registered without an ID), and
HandlerState is the handler's state.

If the callback module exports a system_get_state/1 function, it will be called
in the target process to get its state. Its argument is the same as the Misc
value returned by get_status/1,2, and the system_get_state/1 function is
expected to extract the callback module's state from it. The system_get_state/1
function must return {ok, State} where State is the callback module's state.

If the callback module does not export a system_get_state/1 function,
get_state/1,2 assumes the Misc value is the callback module's state and returns
it directly instead.

If the callback module's system_get_state/1 function crashes or throws an
exception, the caller exits with error {callback_failed, {Module,
system_get_state}, {Class, Reason}} where Module is the name of the callback
module and Class and Reason indicate details of the exception.

The system_get_state/1 function is primarily useful for user-defined behaviours
and modules that implement OTP special processes. The gen_server, gen_fsm, and
gen_event OTP behaviour modules export this function, and so callback modules
for those behaviours need not supply their own.
