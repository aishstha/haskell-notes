
# haskell-notes

## Third class : Defining Functions

### Conditional Expression
In Haskell you write a conditional you write if then else. 
           - In Haskell conditionals are expressions, not statements.
           - Haskell programmers rather write guarded equations than conditional expressions.
```   
abs :: Int -> Int
abs n = if n >= 0 then n else -n
Condiitonal statement must always have an else branch.
```
Nested condition
```
signun n = if n < 0 the -1 else
            if n == 0 then 0 else 1
```
Guarded Equation (preferred by Haskell people)
Function starts with a conditional.
```
abs n | n >= 0          = n 
      | otherwise       = -n
```
The absolute value of n is n when n is greater than or equal to 0 or it's -n otherwise. And otherwise is just another alias for false. 

Guarded equations can be used t make definitions involvign multiple conditions easier to read.

```
signun n | n < 0        = -1
         | n == 0       = 0
         | otherwise    = 1
```
Pattern matching (define functions using pattern matching)
In Haskell you can use pattern matching directly when you define functions. _ is placeholder while doing pattern matching, ie can be anyvalue.
```
not False = True
(&&) :: Bool -> Bool -> Bool
_ && _ = False

AND GATE:

True && b = b
False && _ = False

```
Imp because:
- It avoids evaluating the second argument if the first argument is False.
- Patterns are matched in order. Left to right, top to button.
- Define functions over lists using pattern matching:
```
_ && _ = False
True && True = True
```
- Patterns may not repeat variables. 
```
ERROR CASE:

b && b = b
_ && _ = False
```
List Patterns
```
[1,2,3,4]
MEANS:
1:(2:(3:(4:[])))

head :: [a] -> a
MEANS
head (x:_) = x

tail :: [a] -> [a]
MEANS
tail (_:xs) = xs

head and tail map any non-empty list to its first and remaining elements.
```
* x:xs patterns only match non-empty lists
> head [] = ERROR
* x:xs patterns must be parenthesised, because application has priority over (:). 
> head x:_ = x = ERROR

---

### Lambda expression
- Functions can be constructed without naming the functions by usinig lambda expressions.
- It conveys actualy meaning of curried function.
- They are expressions that denote functions. Function has no name, so it's an expression of function type. 
```
 λx = x + x [the nameless function that takes a number x and returns the result x+x]
 \x = λx in code
 
 This is math is, x -> x+x
 ```
 Advantage:
-They allow you to express your intent better when you're currying functions. Example:
```
add x y = x + y [This is syntatic sugar]
add = λx -> (λy -> x + y)

Add is a function that takes a parameter x, returns a function that takes a parameter y and then adds them together.
```
- Useful when defining functions that return functions as results.
```
const :: a -> b -> a
const x _ = x

const :: a -> (b -> a) [if we define a constant function so this is a function that given an 'a' will return a function that whatever b you give it, will return that a]
const x = λ_ -> x  [defined: const of x returns a function that will, whatever you give it, just ignore it and return x]
```
Idiomatic haskell
```
odds n = map f [0..n-1]
	where
	     f x = x*2 + 1

odds n = map (\x -> x*2 + 1) [0..n--1]

For example: if I want to map a function over a list, there is no reason I should give that function here a name f. And what does f say anyway?
So instead, what I can do, I can just pass a lambda expression to the map and that will be used to map this function over the list.
```
---

### Sections
> (+) 1 2
> (+2) 1 2
> (1+) 2

Advantage:
- No need to write lambda x -> x divided by 2. 
- Allows you to write without inventing names.
- (/2) = half 
- (1\) = reciprocation function

Covered Chapter 4 from Programming in Haskell by Graham Hutton by reading chapters 2, 3 and 4 from the Haskell Language Specification.
