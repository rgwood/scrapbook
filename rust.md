# Rust

## Installation

```
> curl https://sh.rustup.rs -sSf | sh

info: downloading installer

Welcome to Rust!

This will download and install the official compiler for the Rust programming 
language, and its package manager, Cargo.

It will add the cargo, rustc, rustup and other commands to Cargo's bin 
directory, located at:

  /Users/reillywood/.cargo/bin

This can be modified with the CARGO_HOME environment variable.

Rustup metadata and toolchains will be installed into the Rustup home 
directory, located at:

  /Users/reillywood/.rustup

This can be modified with the RUSTUP_HOME environment variable.

This path will then be added to your PATH environment variable by modifying the
profile file located at:

  /Users/reillywood/.profile

You can uninstall at any time with rustup self uninstall and these changes will
be reverted.

Current installation options:

   default host triple: x86_64-apple-darwin
     default toolchain: stable
  modify PATH variable: yes
```

## Programming

Vectors are like arrays, but their size can change with `push()` calls

## Memory

Stack: includes function parameters and local variables

Heap: main memory, for variables of unknown size

Heap is slower because the OS has to do some accounting overhead to check where memory is available etc. Also accessing it involves pointer indirection

## Ownership

Rust ownership: all about managing heap data

Ownership rules
1. Each variable has 1 owner
2. Can only be 1 owner at a time
3. When the owner goes out of scope, value will be dropped

Standard data types are all stored on the stack

String are stored on the heap

Assignment can be a move (for heap data types) or a copy (for stack data types). Cheap+easy to copy stack datam

Moving or passing a heap variable to a function will cause the original to be no longer valid. Simple explanation: assigning a value to another variable changes its ownership.

Can return value and its ownership manually, but that is quite tedious.

## References

References are immutable by default.

Can only have 1 mutable reference to a var at a time

Can always use curly brackets to create scopes 

References’ scopes end the last time they are used - even before explicit scope ends

Slices are inclusive, exclusive. Grr

## Error handling

Can match on Result types to handle things very explicitly
Calling `unwrap()` or `expect()` on a result panics if `Err`. Usually best to  use `expect()` b/c you give it an error message to use when panicking
