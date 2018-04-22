### Parametric Polymorphism

<br />

#### Restricting Implementations Even Further

---

### Type-Kwon-Do

- Implement the function with the following signature:

```haskell
foo :: (x -> y) -> (y -> (w, z)) -> x -> w
```

---

### Type-Kwon-Do Revisited

- Implement the function with the following signature:

```haskell
foo :: (x -> y) -> (y -> (w, z)) -> x -> w

foo xToY yToWZ x = fst (yToWZ (xToY x))

foo xToY yToWZ = fst . yToWZ . xToY
```
@[1](Function signature)
@[1,3](Implementation)
@[1,5](Pointfree style)

---

### Thanks!
