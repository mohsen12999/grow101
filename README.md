# Grow 101

a simple project for learn and grow.

start learning Haskell from [learn you a haskell](https://learnyouahaskell.github.io/).

## Commands

- `ghcup`: package manager
  - `ghcup tua`: Start the interactive GHCup UI
  - `ghcup instal [package]`: install package
- `ghci` : interactive compiler
  - `:l file`:  load `file.hs`
  - `:r`: reload file.

## Arithmetic

```hs
2 + 15  
49 * 100  
1892 - 1472  
5 / 2  
```

## logic

```hs
True && False       --False  
True && True        --True  
False || True       --True  
not False           --True  
not (True && True)  --False  
```

```hs
5 == 5              --True  
1 == 0              --False  
5 /= 5              --False  
5 /= 4              --True  
"hello" == "hello"  --True  
```

## Functions

- function_name arg1 arg2 ,...

```hs
succ 8       --9 (increase one number. equal to ++ in c )
min 9 10     --9
max 100 101  --101
succ 9 + max 5 4 + 1      --16
(succ 9) + (max 5 4) + 1  --16
```

### Define Function

```hs

doubleMe x = x + x  --define function

doubleMe 9    --18
doubleMe 8.3  --16.6

doubleUs x y = x*2 + y*2 --define function

doubleUs 4 9                   --26  
doubleUs 2.3 34.2              --73.0  
doubleUs 28 88 + doubleMe 123  --478  

doubleUs x y = doubleMe x + doubleMe y
```
