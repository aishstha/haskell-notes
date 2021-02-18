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

