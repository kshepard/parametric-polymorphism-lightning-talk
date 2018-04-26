### Parametric Polymorphism

<br />

#### Restricting Implementations Even Further

---

#### Overview

- Parametric Polymorphism: the concept of generic types |
- Extra powerful when paired with immutability and purity |

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
@[1-2]
@[1-2,4-5]
@[1-2,7-8]
@[1-2,10-11]
@[1-2,13-14]

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
- "foo :: a -> b"
  - "a" and "b" aren't necessarily the same thing |

---

#### Let's Implement It

```haskell
foo :: a -> a
```

- The function takes an "a" and also returns an "a" |
- Should be similar to the "Int -> Int" example |
- Easy, we can just return any "a" |
- Like "Int", we can just summon any old "a" from the void |
- Except we don't know what "a" is, so how do we summon it? |
- Hmmmmmm... |

---

#### Let's Implement It

```haskell
foo :: a -> a
```

- Well, an "a" is passed into the function |
- That is the only "a" we can know about |
- There is only one implementation of this function |
- This is the "identity" function |
- It seems useless, but actually comes up a lot |

---

#### More examples

```haskell
foo :: a -> a -> a

foo :: a -> b -> a

foo :: [a] -> Maybe a

```

@[1]
@[3]
@[5]

---

#### Type-Kwon-Do Revisited

- Implement the function with the following signature:

```haskell
foo :: (x -> y) -> (y -> (w, z)) -> x -> w

foo xToY yToWZ x = fst (yToWZ (xToY x))
```
@[1]
@[1,3]

---

### Summing up

- There's a cost of being specific |
- The less we know about the types, the more we know about what it does |
- The more we know about the types, the less we know about what it does |
- Don't even need to look at the implementation: we know exactly what it does |
- Purity + immutability + parametric polymorphism = reasoning superpowers |

---

### Thanks!
