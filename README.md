
# haskell-notes

## second class : Type and Type class
* Type starts with uppercase and type variable starts with lowercase -  length :: [a] -> Int
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
>mult x y z 
MEANS >((mult x) y) z
Unless you're using explicit tuples, all functions in Haskell are normally defined in curried form.

## Type classes and polymorphic functions
Polymorphic functions are functions that are not defined on concrete types but that are defined using type variables.
> length :: [a] -> Int

For any type, length takes a list of calues of type a and returns an integer

> length [1,2,3]
Result: 4

###syntax
```
head :: [a] -> a
take :: Int -> [a] -> [a]

*Main> take 1 [1,2,3]
[1]

```
take takes a number and a list, takes the first n elements from the list and returns that list.

```
zip :: [a] -> [b] -> [(a,b)]

*Main> zip [1,2,3] [4,5,6]
[(1,4),(2,5),(3,6)]
```
zip takes the two lists and takes each element of these two lists and combines them into a tuple. 

```
id :: a -> a

*Main> id 1
1
*Main> id 'a'
'a'
```
Identity function returns it's value. Reference Phill Wadler's paper 'Theorems for Free'

## Overloaded Function
A polymorphic function is called overloaded if its type contains one or more class constraints
> sum :: Num a => [a] -> a
For any numeric type a, sum takes a list of values of type a and returns a value of type a.
