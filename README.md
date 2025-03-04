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

```hs
doubleSmallNumber x = if x > 100  
                        then x  
                        else x*2

doubleSmallNumber' x = (if x > 100 then x else x*2) + 1
```

## List

```hs
lostNumbers = [4,8,15,16,23,42]

-- (++ for concat to array)
[1,2,3,4] ++ [9,10,11,12]  --[1,2,3,4,9,10,11,12]
"hello" ++ " " ++ "world"  --"hello world"
['w','o'] ++ ['o','t']     --"woot"

-- (: for add element to)
'A':" SMALL CAT"  --"A SMALL CAT"
5:[1,2,3,4,5]     --[5,1,2,3,4,5]

-- (!! for get element by index)
"Steve Buscemi" !! 6             --'B'
[9.4,33.2,96.2,11.2,23.25] !! 1  --33.2
```

### Lists Contain Lists

```hs
b = [[1,2,3,4],[5,3,3,3],[1,2,2,3,4],[1,2,3]]

b ++ [[1,1,1,1]]  -- [[1,2,3,4],[5,3,3,3],[1,2,2,3,4],[1,2,3],[1,1,1,1]]  
[6,6,6]:b         -- [[6,6,6],[1,2,3,4],[5,3,3,3],[1,2,2,3,4],[1,2,3]]  
b !! 2            -- [1,2,2,3,4]   
```

### Compare Lists

```hs
[3,2,1] > [2,1,0]       --True  
[3,2,1] > [2,10,100]    --True  
[3,4,2] > [3,4]         --True  
[3,4,2] > [2,4]         --True  
[3,4,2] == [3,4,2]      --True  
```
