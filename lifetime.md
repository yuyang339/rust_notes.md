## every reference has a lifetime
input lifetime: Lifetimes on function or method parameters are called input lifetimes

output lifetime: lifetimes on return values are called output lifetimes.

## three rules (that compiler uses)
compiler uses to figure out what lifetimes references have when there aren’t explicit annotations.

### The first rule
each parameter that is a reference gets its own lifetime parameter.
In other words, a function with one parameter gets one lifetime parameter: 
```rust
fn foo<'a>(x: &'a i32); 
```
a function with two parameters gets two separate lifetime parameters: 
```rust
fn foo<'a, 'b>(x: &'a i32, y: &'b i32); 
```
and so on.

### The second rule 
if there is exactly one input lifetime parameter, 
that lifetime is assigned to all output lifetime parameters: 
```rust
fn foo<'a>(x: &'a i32) -> &'a i32.
```


### The third rule 
if there are multiple input lifetime parameters, 
but one of them is &self or &mut self because this is a method, 
the lifetime of self is assigned to all output lifetime parameters. 
This third rule makes methods much nicer to read and write because fewer symbols are necessary.

## static lifetime
this reference can live for the entire duration of the program. All string literals have the 'static lifetime
this is similiar to static keyword in C++
