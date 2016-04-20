---
layout: post
title:  "Erlang gen_fsm: stop/terminate"
date:   2016-04-19 07:17:21 +0200
categories: erlang eunit
---

{% highlight erlang linenos %}
handle_sync_event(cancel, _From, _StateName, S = #state{}) ->
    {stop, cancelled, ok, S};
{% endhighlight %}

![gen_fsm_terminate]({{site.url}}/assets/20160419/gen_fsm_terminate.png)

#### stop(FsmRef) -> ok

#### stop(FsmRef, Reason, Timeout) -> ok

Orders a generic FSM to exit with the given Reason and waits for it to
terminate. The gen_fsm will call Module:terminate/3 before exiting.

The function returns ok if the generic FSM terminates with the expected reason.
Any other reason than normal, shutdown, or {shutdown,Term} will cause an error
report to be issued using error_logger:format/2. The default Reason is normal.

Timeout is an integer greater than zero which specifies how many milliseconds
to wait for the generic FSM to terminate, or the atom infinity to wait
indefinitely. The default value is infinity. If the generic FSM has not
terminated within the specified time, a timeout exception is raised.

If the process does not exist, a noproc exception is raised.


{% highlight erlang linenos %}
handle_sync_event(cancel, _From, _StateName, S = #state{}) ->
    {stop, normal, ok, S};
{% endhighlight %}
