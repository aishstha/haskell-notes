
# haskell-notes

## Third class : Defining Functions

### Conditional Expression
In Haskell you write a conditional you write if then else. 
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
Pattern matching
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
```
_ && _ = False
True && True = True
```
- Patterns may ot repeat variables.
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


