# rust_notes.md
Learning notes on Rust

Rust is a statically typed language, which means that it must know the types of all variables at compile time.

## chapter3 Variables and Mutability

let vs let mut

const var must be annotated with type

const and var cannot be used together

shadowing: for mutable variables, shadowing may cause errors if the type the first variable and the type of the second variable are different

tuple: similar to struct in C. it can have differnt types. the element of a tuple can be accessed by using a period (.) followed by the index of the value we want to access.

array: must have the same type

loop {
}

while condition {
}

for var in iterator {
}

## chapter4 Ownership
Rules:
- Each value in Rust has a variable that’s called its owner.
- There can only be one owner at a time.
- When the owner goes out of scope, the value will be dropped.

stack data: copy
heap data: shallow copy - move
deep copy - clone
simple scalar values can be Copy

reference: & doesn't take ownership

bowrrowing: having references as function parameters is called borrowing

mutable reference: mutable references have one big restriction: you can have only one mutable reference to a particular piece of data in a particular scope.
let r1 = &mut s;
let r2 = &mut s;

immutable reference: We’re not allowed to modify something we have a reference to.

if a variable is borrowed by a immutable reference, it cannot be borrowed by a mutable references
let r1 = &s; // no problem
let r2 = &s; // no problem
let r3 = &mut s; // BIG PROBLEM

slice: a[0..3]

The type that signifies “string slice” is written as &str

## chapter6 Struct

struct is similiar to tuple. like tuple, the elements of a struct can be different types.
unlike tuple, an element of a struct can have a name.

define a struct:
struct struct_name {
  element_name1: type1,
  element_name2: type2,
}

instantiate a struct:
struct_name {
  element_name1: value,
  element_name2: value,
}

define a method associated with the struct

impl struct_name {
  fn func_name(args) -> return_type {
    func_body
  }
}


## chapter7 enum

enum enum_type {
  variant1,
  variant2
}

this custom data type enum_type has two variants
when we instantiate variants, we 
