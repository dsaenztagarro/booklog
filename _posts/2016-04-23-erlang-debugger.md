---
layout: post
title:  "Erlang EUnit"
date:   2016-04-09 11:17:21 +0200
categories: erlang eunit
---

`debugger:start()`

Default timeout of Eunit is 5 seconds. In order to use debugger you will need
to increase Eunit timeout.

{% highlight erlang linenos %}
started_properly_test_() ->
    {"The fsm2 is started propertly in idle status",
     ?setup(fun valid_initial_status2/1)}.

% Instantiator

valid_initial_status2(Pid) ->
    {timeout, 3600, [
    fun() ->
        {CurrentStateName, _CurrentStateData} = sys:get_state(Pid),
        ?assertEqual(idle, CurrentStateName)
    end
    ]}.
{% endhighlight %}

