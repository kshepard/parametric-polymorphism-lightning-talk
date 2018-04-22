### Parametric Polymorphism

<br />

#### Restricting Implementations Even Further

---

#### Type-Kwon-Do

- Implement the function with the following signature:

```haskell
foo :: (x -> y) -> (y -> (w, z)) -> x -> w
```

---

#### Starting With Something Concrete

```haskell
-- Function that takes an integer, and returns an integer
foo :: Int -> Int

-- This might be a square function:
foo i = i * i

-- Or a doubling function
foo i = 2 * i

-- Or maybe something like mod 2
foo i = i `mod` 2

-- Or it can return a constant
foo i = 42
```
@[1-2](Function signature)
@[1-2,4-5](Square)
@[1-2,7-8](Double)
@[1-2,10-11](Mod2)
@[1-2,13-14](Constant)

---

#### Enter Parametric Polymorphism

```haskell
foo :: a -> a
```

- Here 'a' is a parametrically polymporhic type, which means it can represent any type. |
- There's nothing special about 'a', except that it starts with a lowercase letter. |

---

#### Enter Parametric Polymorphism

```haskell
foo :: a -> a

foo :: b -> b

foo :: something -> something
```

- These are all equivalent |
- Important note: the first and second "a" must be the same type |
- "foo :: a -> b" |
  - "a" and "b" aren't necessarily the same thing |

---

#### Type-Kwon-Do Revisited

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
