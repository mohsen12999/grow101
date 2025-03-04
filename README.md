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
