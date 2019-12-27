## definition
similar to interface in Java
define a set of shared behaviours by grouping methods together

```rust
pub trait xxx {
  fn method1(params) -> return_type; // no implementation
}
```

## implement a trait for a type
```rust
implement xxx for yyy {
  fn method1(params) -> return_type {
    // concrete code
  }
}

```

## default implementation
we can specify default implementation for methods
```rust
pub trait xxx {
  fn method1(params) -> return_type {
    // concrete implementation
  }
}
```

## traits as parameters
If we pass traits as parameters to a function, the function accepts any type that implements the specified trait

```rust
fn zzz(item: impl xxx) {
  // item can be any type that implements xxx trait
}
```

## trait bound
```rust
fn zzz<T: xxx>(item: T){
}
```

if zzz has multiple parameters, different parameters can have different types that implement the same specified trait
```rust
fn zzz(item1: impl xxx, item2: impl xxx)
```

we want to force parameters to have the same type
```rust
fn zzz<T: xxx>(item1: T, item2: T){

}
```
## multiple bounds
```rust
fn zzz<T: xxx1+xxx2>(item1: T){

}
```

```rust
fn zzz<T: xxx1+xxx2, U: xxx3+xxx4>(item1: T, item2: U){

}
```

```rust
fn zzz<T, U>(item1: T, item2: U){
  where T: xxx1+xxx2, U: xxx3+xxx4
}
```

## return type that implements traits
note that we can only use impl Trait if we’re returning a single type.
```rust
fn zzz<T, U>(item1: T, item2: U) -> impl xxx {
}
```
