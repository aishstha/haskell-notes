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



