## Currying

Currying is the process of transforming a function that takes multiple arguments in a tuple as its argument, into a function that takes just a single argument and returns another function which accepts further arguments, one by one, that the original function would receive in the rest of that tuple.

```
f :: a -> (b -> c)     -- which can also be written as    f :: a -> b -> c
```
is the curried form of
```
g :: (a, b) -> c
```
You can convert these two types in either directions with the Prelude functions curry and uncurry.
```
f = curry g
g = uncurry f
```
Both forms are equally expressive. It holds
```
f x y = g (x,y)    
```
however the curried form is usually more convenient because it allows partial application.

In Haskell, all functions are considered curried: That is, all functions in Haskell take just one argument. This is mostly hidden in notation, and so may not be apparent to a new Haskeller. It can be said that arrows in the types notation associate to the right, so that 
```
f :: a -> b -> c is really f :: a -> (b -> c)
```
Functional application, correspondingly, associates to the left: f x y is really (f x) y, so the types fit.

As an illustration, let's take the function
```
div :: Int -> Int -> Int    -- which is actually Int -> (Int -> Int)
```
which performs integer division. The expression div 11 2 unsurprisingly evaluates to 5.
But there's more going on here than immediately meets the untrained eye. It could be a two-part process.

On its own, div 11 is a function of type``` Int -> Int```. Then that resulting function can be applied to the value 2, so (div 11) 2 yields 5. Of course an optimizing compiler will probably handle that whole expression at once, but conceptually that's what's going on.

You'll notice that the notation for types reflects this: you can read ```Int -> Int -> Int``` incorrectly as "takes two Ints and returns an Int", but what it's really saying is "takes an Int and returns something of the type ```Int -> Int``` -- that is, it returns a function that takes an Int and returns an Int. (One can write the type as ```Int x Int -> Int``` if you really mean the former -- but since all functions in Haskell are curried, that's not legal Haskell. Alternatively, using tuples, you can write ```(Int, Int) -> Int```, but keep in mind that the tuple constructor (,) itself can be curried.)

Much of the time, currying can be ignored by the new programmer. The major advantage of considering all functions as curried is theoretical: formal proofs are easier when all functions are treated uniformly (one argument in, one result out). Having said that, there are Haskell idioms and techniques for which you need to understand currying.

