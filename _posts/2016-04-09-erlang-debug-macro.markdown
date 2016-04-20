---
layout: post
title:  "EUnit Erlang"
date:   2016-04-09 11:17:21 +0200
categories: erlang eunit
---

`debugger:start()`

## Debugging macros

```erlang
-module(trade_fsm).
-include_lib("eunit/include/eunit.hrl").
% ...
idle(Event, Data) ->
    ?debugMsg(">>> idle"),
```

**debugHere**
Just prints a marker showing the current file and line number. Note that this is an argument-less macro. The result is always ok.

**debugMsg(Text)**

Outputs the message Text (which can be a plain string, an IO-list, or just an
atom). The result is always ok.

**debugFmt(FmtString, Args)**

This formats the text like io:format(FmtString, Args) and outputs it like
debugMsg. The result is always ok.

**debugVal(Expr)**

Prints both the source code for Expr and its current value. E.g.,
?debugVal(f(X)) might be displayed as "f(X) = 42". (Large terms are shown
truncated.) The result is always the value of Expr, so this macro can be
wrapped around any expression to display its value when the code is compiled
with debugging enabled.

**debugTime(Text,Expr)**

Prints Text and the wall clock time for evaluation of Expr. The result is
always the value of Expr, so this macro can be wrapped around any expression to
show its run time when the code is compiled with debugging enabled. For
example, List1 = ?debugTime("sorting", lists:sort(List)) might show as
"sorting: 0.015 s".

[EUnit](http://erlang.org/doc/apps/eunit/chapter.html)
[Common Test](http://erlang.org/doc/apps/common_test/basics_chapter.html)
