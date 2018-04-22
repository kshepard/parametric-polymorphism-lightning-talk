# Parametric Polymorphism

### Restricting Implementations Even Further

---

## A1

Test

---

## A2

- Test1
- Test2
- Test3

---

@title[Haskell Code]

<p><span class="slide-title">Haskell Code</span></p>

```haskell
foo :: (x -> y) -> (y -> (w, z)) -> x -> w

foo :: Int -> Int

foo i = i * i

foo i = 2 * i
```

@[1,1](Test1)
@[3-7](Test2)

---

### Thanks!
