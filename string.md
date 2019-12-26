## convert an i32 to a string
```rust
x.to_string();

```

## initialize a vector with empty strings
```rust
let mut vect = vec![String::new(); 126];
```


## reverse a string
### rev() is lazy. So we need to call collect in order to force the computation. Also when we call collect, we need to specify the type it returns.
```rust
y.chars().rev().collect::<String>() 
```

## enumerate a string
```rust
for (i, c) in s.chars().enumerate()

```

## string concatenation
```rust

s.push_str(&str)
s += "xxxx"
```

## check if a string is empty
```rust
s.is_empty() 

```

## split a string
```rust
s.split("delimiter") // return a iterator

```
