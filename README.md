
# haskell-notes

## Defining Functions

### Part - 1
In Haskell, a similar comprehension notation can be used to construct new lists from old lists.

```
[x^2 | x <- [1..5]]
```
The list [1,4,9,16,25] of all numbers x62 such that x is an element of the list [1..5]

set comprehensions

[x^2 | x <- [1..5]]
It's the list of square numbers x squared where x is taken from the list one to five. 

x <- [1..5] IS CALLED GENERATOR. The reason it's called a generator is because it defines how to generate values for x. So x is taken from that set.

## Comprehensions can have multiple generators:
[(x,y) | x <- [1,2,3], y <-[4,5]]
[(1,4),(1,5).....]
+ generators or multiple generators is like a nested loop where y is inner loop and the x is the outer loop. 
+ generators can also depend on each other. Just like when you have a loop, the inner loop can use variables from the outer loop. With comprehensions that's no different:
[(x,y) | x <- [1..3], y <- [x..3]] RESULT: [(1,1).(1,2),(1,3),(2,2),(2,3),(3,3)]
+ WE CAN WRITE CONSIDE CODE WITH GENERATORS
For example, if we want to take a list of lists and flatten them into a single list we can do that with the following comprehension.

## Using a depedant generator we can definie the library function that CONCATENATES a list of lists:

concat :: [[a]] => [a]
concat xss = [x | xs <- xss, x <- xs]

> concat [[1,2,3],[4,5],[6]]

[1,2,3,4,5,6]

Give me every list out of that list of lists.
Then just give me every element of that list
and return that. This is a doubly nested loop that goes over
every list in this list of lists and just
yields all the values to return
a single list of type a, of the same element type
as the original list.

