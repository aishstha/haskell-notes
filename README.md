
# haskell-notes

## second class : Type and Type class

* Type error
* Every syntactically well-formed expression has a type and that type is calculated by the compiler at compile-time using a process called type inference. 
* In haskell type errors are found in complie time.
```
:type "hello"
:t "h"
```

* Basic Types
  * Bool
  * Char  
  * String
  * Int
  * Integer
  * Float
 [t] is the type of lists with elements of type t
 >  ['a','b'] :: [Char]
 List of list of characters:
 >  [['a'],['b','c']] :: [[Char]] 
 
 * Tuple Types: A tuple is a sequence of values of different types
 > (False, 'a', True) :: (Bool, Char, Bool)
    * type of tuple encodes it's size
    * type of values is unresticted
    > ('a', (False, 'b')) :: (Char, (Bool, Char))

### Types of functions
A function is a mapping from values of one type to values of another type
> t1 -> t2 is the type of function that maps values of type t1 to values of type t2
  * t1 = domain * t2 = range
  * 
## Currying function
Look at this type here: add is a function,
here we see that from this arrow,
that takes an integer and returns a function
that takes another integer and returns an integer.
That is currying.Intentet by Haskell B. Curry.

* The function drop takes an integer and returns a function from list to list and what we see here is that we can now define drop 5: we can partially apply drop 5 and it will return a function that will take a list, drop the first five elements and then return the list. 
> take 5 :: [Int] -> [Int]
* For example if we have this function add' that was defined in a curried way, we can define a function that increments a value with 1 by partially applying add' to one. If we look at that type there add' 1 is a function that takes an integer and returns another integer.
> add' 1 :: Int -> Int
*
>mult x y z MEANS >((mult x) y) z
Unless you're using explicit tuples, all functions in Haskell are normally defined in curried form.

