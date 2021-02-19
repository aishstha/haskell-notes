# haskell-notes

## introduction
* haskell script has .hs suffix
* initial setup
  * create test.hs
  * go in terminal of this file location and perform 
    > ghci test

test.hs
```
double x = x + x
quad x = double (double x)
```

```
fm-pc-lt-153@fmpclt153-Predator-PH315-52 ~/Documents/projPersonal/code-snippets (master)$ ghci test
GHCi, version 8.6.5: http://www.haskell.org/ghc/  :? for help
[1 of 1] Compiling Main             ( test.hs, interpreted )
Ok, one module loaded.
*Main> double 2
4
*Main> 
```
:quit
Quits GHCi. You can also quit by typing control-D at the prompt.

:reload
Attempts to reload the current target set (see :load) if any of the modules in the set, or any dependent module, has changed. Note that this may entail loading new modules, or dropping modules which are no longer indirectly required by the target.

```
*Main> take (double 2) [1,2,4]
[1,2,4]
*Main> take (double 2) [1,2,3,4,5,6,7,8]
[1,2,3,4]
```
```
* x `f` y is syntactic sugar for f x y. 
 * x `f` y is infix operator
 * (+) 2 2 is infix form of 2 + 2
```

```
factorial n = product [1..n]
average ns = sum ns `div` length ns
```
Processing: 
``` 
> factorial 10
> avarage [1,2,3,4,5]
```

* function and parameter name must begin with lowercase
  * we can even use regular quotes for function name as well. eg: x'
* type name has to be in uppercase
* xs, that means a list of values of type x and this is a list of values. xss list of list
* haskell identifiers are short so you don't it elements, you call it xs.
* whitespace is significant ie `layout rule` / `implicit grouping`
```
a = b + c
    where 
      b = 1
      c = 2
d = a * 2
```
* useful commands
 * :load name
 * :edit name
 * :edit ---- this edits current scrpit
 * :type expr -----gets type of expression
 * :? ----show all command

Syntax
```
avg = a `div` length xs
    where 
        a = 10  
        xs = [1,2]
```
Result: 5

* Haskell has several types, for instance Boolean values and strings.
* Eg:
  * > not True ----- not is a (predefined) function that negates a Boolean value.
  * > (not False || True) && (False || True)
* Haskell is case-sensitive
*  (++) concatenates two strings.
*  Eg: > "Hello" ++ " " ++ "world" Result: Helloworld
```
*Main> "hello" ++ "world"
"helloworld"
*Main> length ""
0
*Main> head "head"
'h'
*Main> tail "tails"
"ails"
*Main> last "hello"
'o'
*Main> init "hello"
"hell"
*Main> reverse "hello"
"olleh"
*Main> null "hello"
False
```
* https://learning.edx.org/course/course-v1:DelftX+FP101x+3T2015/block-v1:DelftX+FP101x+3T2015+type@sequential+block@ea7afa9c5b924b96b05951cbcff001b2/block-v1:DelftX+FP101x+3T2015+type@vertical+block@6bff21c463674dca99826289f679d8a2
* If you try to use logical negation on a string, you get error. > not "hello"
* Every Haskell expression has a type, and there is an interpreter command to ask for that type.
  > :t True Result: True :: Bool
* In Haskell, strings are just lists of single characters, and the notation "Hello" is actually just an abbreviation for a notation that makes the list-like character much more obvious
  > :t "Hello" Result: "Hello" :: [Char]
  > ['H', 'e', 'l', 'l', 'o']
  > :t ['H', 'e', 'l', 'l', 'o']
  > 'H'
  > :t 'H'
  
```
*Main> :t head "Hello"
   head "Hello" :: Char
  *Main> :t tail "Hello"
   tail "Hello" :: [Char]
```
* > :t length

length :: [a] -> Int

The result is somewhat surprising. The function returns an integer (i.e., an Int), ok. But it doesn’t take a string, i.e., a [Char], but instead a [a]? What does the a mean? It means that 'a' is a type variable. We can choose any type to take a’s place! So length computes the length of any list – not just lists of characters, but also lists of numbers, or even lists of lists. 
