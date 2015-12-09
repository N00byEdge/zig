# zig lang

An experiment in writing a low-level programming language with the intent to
replace C. Zig intends to be a small language, yet powerful enough to write
optimal, readable, safe, and concise code to solve any computing problem.

Porting a C project to Zig should be a pleasant experience - every C feature
needs a corresponding Zig feature which solves the problem equivalently or
better.

Zig is not afraid to roll the major version number of the language if it
improves simplicity, fixes poor design decisions, or adds a new feature which
compromises backward compatibility.

## Goals

 * Completely compatible with C libraries with no wrapper necessary.
 * In addition to creating executables, creating a C library is a primary use
   case. You can export an auto-generated .h file.
 * Do not depend on libc unless explicitly imported.
 * Provide standard library which competes with the C standard library and is
   always compiled against statically in source form.
 * Generics so that one can write efficient data structures that work for any
   data type.
 * Ability to run arbitrary code at compile time and generate code.
 * A type which represents an error and has some convenience syntax with
   regards to resources.
 * Defer statement.
 * Memory zeroed by default, unless you explicitly ask for uninitialized memory.
 * Eliminate the need for configure, make, cmake, etc.
 * Eliminate the need for header files (when using zig internally).
 * Tagged union enum type.
 * Resilient to parsing errors to make IDE integration work well.
 * Source code is UTF-8.
 * Ability to mark functions as test and automatically run them in test mode.
   This mode should automatically provide test coverage.
 * Friendly toward package maintainers.
 * Ability to declare dependencies as Git URLS with commit locking (can
   provide a tag or sha1).
 * Include documentation generator.
 * Shebang line OK so language can be used for "scripting" as well.

### Current Status

 * Core language features are lacking such as structs, enums, loops.
 * Only Linux is supported.
 * Only building for the native target is supported.
 * Have a look in the examples/ folder to see some code examples.
 * Optimized machine code that Zig produces is indistinguishable from
   optimized machine code produced from equivalent C program.
 * Zig can generate dynamic libraries, executables, object files, and C
   header files.
 * The binaries produced by Zig have complete debugging information so you can,
   for example, use GDB to debug your software.

### Roadmap

 * structs
 * loops
 * enums
 * inline assembly and syscalls
 * conditional compilation and ability to check target platform and architecture
 * main function with command line arguments
 * void pointer constant
 * sizeof
 * address of operator
 * global variables
 * static initializers
 * assert
 * function pointers
 * hex literal, binary literal, float literal, hex float literal
 * += and -= operators
 * fix a + b + c
 * running code at compile time
 * standard library print functions
 * panic! macro or statement that prints a stack trace to stderr in debug mode
   and calls abort() in release mode
 * unreachable codegen to panic("unreachable") in debug mode, and nothing in
   release mode
 * implement a simple game using SDL2
 * implement a GUI with several types of widgets and investigate whether we need
   any OOP features

## Building

```
mkdir build
cd build
cmake ..
make
./run_tests
```
