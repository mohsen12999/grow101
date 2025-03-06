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

### List functions

- `head` takes a list and returns its head. The head of a list is basically its first element.

```hs
head [5,4,3,2,1]  --5   
```

- `tail` takes a list and returns its tail. In other words, it chops off a list's head.

```hs
tail [5,4,3,2,1]  --[4,3,2,1]    
```

- `last` takes a list and returns its last element.

```hs
last [5,4,3,2,1]  --1
```

- `init` takes a list and returns everything except its last element.

```hs
init [5,4,3,2,1]  --[5,4,3,2]
```

- `length` takes a list and returns its length, obviously.

```hs
length [5,4,3,2,1]  --5
```

- `null` checks if a list is empty. If it is, it returns True, otherwise it returns False.

```hs
null [1,2,3]  --False  
null []       --True  
```

- `reverse` reverses a list.

```hs
reverse [5,4,3,2,1]  --[1,2,3,4,5]  
```

- `take` takes a number and a list. It extracts that many elements from the beginning of the list.

```hs
take 3 [5,4,3,2,1]  --[5,4,3]  
take 1 [3,9,3]      --[3]  
take 5 [1,2]        --[1,2]  
take 0 [6,6,6]      --[]  
```

- `drop` works in a similar way, only it drops the number of elements from the beginning of a list.

```hs
drop 3 [8,4,2,1,5,6]  --[1,5,6]  
drop 0 [1,2,3,4]      --[1,2,3,4]  
drop 100 [1,2,3,4]    --[]   
```

- `minimum` and `maximum`

```hs
minimum [8,4,2,1,5,6]  --1  
maximum [1,9,2,3,4]    --9   
```

- `sum` and `product`

```hs
sum [5,2,1,6,3,2,5,7]      --31  
product [6,2,1,2]          --24  
product [1,2,5,6,7,9,2,0]  --0   
```

- `elem` takes a thing and a list of things and tells us if that thing is an element of the list. It's usually called as an infix function because it's easier to read that way.

```hs
4 `elem` [3,4,5,6]   --True  
10 `elem` [3,4,5,6]   --False  
```

## Ranges

define ranges

```hs
[1..20]      --[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20]  
['a'..'z']   --"abcdefghijklmnopqrstuvwxyz"  
['K'..'Z']   --"KLMNOPQRSTUVWXYZ"   
```

define special series

```hs
[2,4..20]  --[2,4,6,8,10,12,14,16,18,20]  
[3,6..20]  --[3,6,9,12,15,18]
```

```hs
-- [20..1] is wrong
[20,19...1]
```

```hs
[0.1, 0.3 .. 1]  --[0.1,0.3,0.5,0.7,0.8999999999999999,1.0999999999999999]  
```
