## initialize a hashmap
```rust
let mut m = HashMap::new()
let mut map: HashMap<&str, i32> = HashMap::with_capacity(10);
```

## enumerate a hashmap
```rust
for (key, val) in &m {
}
```

## check if hashmap contains key
```rust
m.contains_key(&k)
```

## insert new element into hashmap
```rust
m.insert(key, val)
```
