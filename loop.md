## for loop
```rust
for x in 1..10 // 1,2,3..9
for x in 1..=10 // 1,2,3..10
```

## for loop with custom step
```rust

for x in (1..10).step_by(2) {
        println!("{}", x);
```

## reverse a loop
```rust
for i in 1..10.rev() // 9, 8, ... 1
```

## for iter 
### Borrows each element of the collection through each iteration. Thus leaving the collection untouched and available for reuse after the loop.
```rust
for x in iterable.iter()
```

## for iter_mut
### mutably borrows each element of the collection, allowing for the collection to be modified in place.
```rust
for x in iterable.iter_mut()
```

## for into_iter
### consumes the collection so that on each iteration the exact data is provided. Once the collection has been consumed it is no longer available for reuse as it has been 'moved' within the loop.
``` rust
for x in iterable.into_iter()
```
