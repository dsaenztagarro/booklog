---
layout: post
title:  "C"
date:   2016-03-21 05:00:00 +0100
categories: language
---

### Parsing string options

```c
#include <string.h> // for strtok

  char *token = strtok(input, ",");
  while(token) {
          puts(token);
          token = strtok(NULL, ",");
  }
```

# Links

- [The NetBSD Project/Wiki](https://wiki.netbsd.org/tutorials/)

## Tools

- [Indent](https://www.gnu.org/software/indent/)
- [Valgrind](http://valgrind.org)

```
# -din  Specifies the indentation, in character positions, of global variable names and all struct/union member
#       names relative to the beginning of their type declaration.  The default is -di16.
indent -di1 src/main.c
```

```
==11278== LEAK SUMMARY:
==11278==    definitely lost: 2,401 bytes in 14 blocks
==11278==    indirectly lost: 5,192 bytes in 19 blocks
==11278==      possibly lost: 1,670 bytes in 55 blocks
==11278==    still reachable: 12,102 bytes in 134 blocks
==11278==         suppressed: 75,503 bytes in 171 blocks
==11278== Reachable blocks (those to which a pointer was found) are not shown.
==11278== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==11278==
==11278== For counts of detected and suppressed errors, rerun with: -v
==11278== ERROR SUMMARY: 54 errors from 54 contexts (suppressed: 13 from 13)
```

## GCC Compiler flags

- `-Wall` tells the compiler to implement 'all' Warning options. Warnings are diagnostic messages that report constructions which are not inherently erroneous but which are risky or suggest there may have been an error. Very useful for debugging code.

- `-ansi` tells the compiler to implement the ANSI language option. This turns off certain "features" of GCC which are incompatible with the ANSI standard.

- `-pedantic` used in conjunction with -ansi, this tells the compiler to be adhere strictly to the ANSI standard, rejecting any code which is not compliant.

- `-o` tells the compiler to save the compiled program under the name . So, typing "gcc myfile.c -o myfile.x" will take the source code of file "myfile.c" and create program "myfile.x" rather than the default program "a.out".

## C functions

- `memset`: Using memset() to zero out a entire structure, rather than initializing individual fields, ensures that any nonstandard fields that are provided by some implementations are also initialized to 0

## Makefile functions

```
COMMON_DEPS := $(subst .c,.o, $(COMMON_SOURCES))
$(COMMON_SOURCES:.c=.o)
```

See Makefile [8.2 Functions for String Substitution and Analysis](https://www.gnu.org/software/make/manual/html_node/Text-Functions.html)

# Project

http://eradman.com/posts/kqueue-tcp.html

# References

- [Learn C the hard way](http://c.learncodethehardway.org/book/ex30.html)
- [GNU make](https://www.gnu.org/software/make/manual/make.html)
- [Cpputest](https://cpputest.github.io)

- [Debugging with GDB](https://www.sourceware.org/gdb/current/onlinedocs/gdb.html)
- [GNU Guile 2.0.12 Reference Manual](https://www.gnu.org/software/guile/manual/)
- [The LLVM Compiler Infrastructure](http://llvm.org)
- [FSEvents C Example](http://stackoverflow.com/questions/11556545/fsevents-c-example)

- [Unit testing C Programs with Mock functions](http://blogs.grammatech.com/unit-testing-c-programs-with-mock-functions)
- [Doing C code unit testing on a shoestring: Part 1- The basics and the tools](http://www.embedded.com/design/programming-languages-and-tools/4007177/2/Doing-C-code-unit-testing-on-a-shoestring-Part-1-The-basics-and-the-tools)
- [Doing C code unit testing on a shoestring: Part 2- Code coverage analysis](http://www.embedded.com/design/prototyping-and-development/4007183/2/Doing-C-code-unit-testing-on-a-shoestring-Part-2-Code-coverage-analysis)
- [Doing C code unit testing on a shoestring: Part 3 - Building a unit test framework](http://www.embedded.com/design/prototyping-and-development/4007187/2/Doing-C-code-unit-testing-on-a-shoestring-Part-3--Building-a-unit-test-framework)

## Compilers

- [Clang 4.0 documentation](http://clang.llvm.org/docs/index.html)

## Libraries

- [libevent – an event notification library](http://libevent.org)

# Library functions

- [Using gnu C __attribute__](http://www.unixwiz.net/techtips/gnu-c-attributes.html)
- [vsnprintf](http://www.ibm.com/support/knowledgecenter/ssw_ibm_i_72/rtref/vsnprintf.htm)

Find information from:

- `man dirent`. Search modules and c functions.
- Inspecting includes files: `/usr/include/dirent.h`, `/usr/include/sys/dirent.h`.

### Command line

```
# Find system headers
clang -x c -v -E /dev/null

getconf GNU_LIBPTHREAD_VERSION
```

Add system headers to vim path (example):

```
set path=/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.12.sdk/usr/include`
```

### Core dumps

By default, the Ubuntu kernel is configured to use apport to log coredumps. You can override this by overwriting /proc/sys/kernel/core_pattern, check the "Naming of core dump files" section in man core for details. For example:

echo '/tmp/core.%e.%p.%t' | sudo tee /proc/sys/kernel/core_pattern

Apport writes core dumps to /var/crash/_path_to_program.userid.crash, BUT it will only do so for applications installed from the main ubuntu apt repositories.
