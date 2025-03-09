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

```hs
mod 10 5  --4
10 `mod` 5 --4
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

### Define Infinite Range

```hs
[13,26..]
```

- `cycle` takes a list and cycles it into an infinite list.

```hs
take 10 (cycle [1,2,3])  --[1,2,3,1,2,3,1,2,3,1]  
take 12 (cycle "LOL ")   --"LOL LOL LOL "   
```

- `repeat` takes an element and produces an infinite list of just that element. It's like cycling a list with only one element.

```hs
take 10 (repeat 5)  --[5,5,5,5,5,5,5,5,5,5]
```

- `replicate` function if you want some number of the same element in a list.

```hs
replicate 3 10 --[10,10,10]
```

## Comprehension List

```hs
[x*2 | x <- [1..10]]  --[2,4,6,8,10,12,14,16,18,20]
```

```hs
[x*2 | x <- [1..10], x*2 >= 12]  --[12,14,16,18,20] 
```

```hs
[ x | x <- [50..100], x `mod` 7 == 3]  --[52,59,66,73,80,87,94] 
```

```hs
-- define function, odd x equal to x `mode` 2 == 0
boomBangs xs = [ if x < 10 then "BOOM!" else "BANG!" | x <- xs, odd x]

boomBangs [7..13]  --["BOOM!","BOOM!","BANG!","BANG!"] 
```

```hs
[ x | x <- [10..20], x /= 13, x /= 15, x /= 19]  --[10,11,12,14,16,17,18,20]  
```

```hs
[ x*y | x <- [2,5,10], y <- [8,10,11]]  --[16,20,22,40,50,55,80,100,110]
[ x*y | x <- [2,5,10], y <- [8,10,11], x*y > 50]  --[55,80,100,110]
```

```hs
nouns = ["hobo","frog","pope"]  
adjectives = ["lazy","grouchy","scheming"]  
[adjective ++ " " ++ noun | adjective <- adjectives, noun <- nouns]  --["lazy hobo","lazy frog","lazy pope","grouchy hobo","grouchy frog","grouchy pope","scheming hobo","scheming frog","scheming pope"]
```

```hs
length' xs = sum [1 | _ <- xs]
```

```hs
removeNonUppercase st = [ c | c <- st, c `elem` ['A'..'Z']]

removeNonUppercase "Hahaha! Ahahaha!"  --"HA"  
removeNonUppercase "IdontLIKEFROGS"   --"ILIKEFROGS"
```

```hs
let xxs = [[1,3,5,2,3,1,2,4,5],[1,2,3,4,5,6,7,8,9],[1,2,4,2,1,6,3,1,3,2,3,6]]  
[ [ x | x <- xs, even x ] | xs <- xxs]  --[[2,2,4],[2,4,6,8],[2,4,2,6,2,6]]  
```

## Tuples

- define with ()

- `fst` takes a pair and returns its first component.

```hs
fst (8,11)          --8  
fst ("Wow", False)  --"Wow"
```

- `snd` takes a pair and returns its second component.

```hs
snd (8,11)          --11  
snd ("Wow", False)  --False  
```

- `zip` It takes two lists and then zips them together into one list by joining the matching elements into pairs.

```hs
zip [1,2,3,4,5] [5,5,5,5,5]  --[(1,5),(2,5),(3,5),(4,5),(5,5)]  
zip [1 .. 5] ["one", "two", "three", "four", "five"]  --[(1,"one"),(2,"two"),(3,"three"),(4,"four"),(5,"five")] 

zip [5,3,2,6,2,7,2,5,4,6,6] ["im","a","turtle"]  --[(5,"im"),(3,"a"),(2,"turtle")] 

zip [1..] ["apple", "orange", "cherry", "mango"]  --[(1,"apple"),(2,"orange"),(3,"cherry"),(4,"mango")]  
```

```hs
triangles = [ (a,b,c) | c <- [1..10], b <- [1..10], a <- [1..10] ]

rightTriangles = [ (a,b,c) | c <- [1..10], b <- [1..c], a <- [1..b], a^2 + b^2 == c^2]

rightTriangles' = [ (a,b,c) | c <- [1..10], b <- [1..c], a <- [1..b], a^2 + b^2 == c^2, a+b+c == 24]  
rightTriangles'  --[(6,8,10)]
```

## Type

```hs
:t 'a'          --'a' :: Char  
:t True         --True :: Bool  
:t "HELLO!"     --"HELLO!" :: [Char]  
:t (True, 'a')  --(True, 'a') :: (Bool, Char)  
:t 4 == 5       --4 == 5 :: Bool 
```

```hs
removeNonUppercase :: [Char] -> [Char]  
removeNonUppercase st = [ c | c <- st, c `elem` ['A'..'Z']]  
```

```hs
addThree :: Int -> Int -> Int -> Int  
addThree x y z = x + y + z  
```

- `Int` stands for integer. `Int` is bounded, which means that it has a minimum and a maximum value. Usually on 32-bit machines the maximum possible Int is 2147483647 and the minimum is -2147483648.

- `Integer` for bounded integer number.

```hs
factorial :: Integer -> Integer  
factorial n = product [1..n]

factorial 50  --30414093201713378043612608166064768844377641568960512000000000000  
```

- `Float` is a real floating point with single precision.

```hs
circumference :: Float -> Float  
circumference r = 2 * pi * r  

circumference 4.0  --25.132742
```

- `Double` is a real floating point with double the precision!

```hs
circumference' :: Double -> Double  
circumference' r = 2 * pi * r

circumference' 4.0  --25.132741228718345
```

- `Bool` is a boolean type. It can have only two values: True and False.

- `Char` represents a character. It's denoted by single quotes. A list of characters is a string.

## TypeClass

- `Eq` is used for types that support equality testing.

```hs
5 == 5  --True  
5 /= 5  --False  

'a' == 'a'          --True  
"Ho Ho" == "Ho Ho"  --True  
3.432 == 3.432      --True  
```

- `Ord` is for types that have an ordering.
- `Ordering` is a type that can be GT, LT or EQ, meaning greater than, lesser than and equal,

```hs
:t (>)  -- (>) :: (Ord a) => a -> a -> Bool  

"Abrakadabra" < "Zebra"         --True  
"Abrakadabra" `compare` "Zebra"  --LT  
5 >= 2         --True  
5 `compare` 3  --GT  
```

- `Show` the member can be presented as strings.

```hs
show 3      --"3"  
show 5.334  --"5.334"  
show True   --"True"
```

- `Read` is sort of the opposite typeclass of Show.

```hs
read "True" || False     --True  
read "8.2" + 3.8         --12.0  
read "5" - 2             --3  
read "[1,2,3,4]" ++ [3]  --[1,2,3,4,3]
```

```hs
read "4" --make error. need type
```

```hs
:t read  --read :: (Read a) => String -> a  
```

```hs
read "5" :: Int    --5  
read "5" :: Float  --5.0  
(read "5" :: Float) * 4  --20.0  
read "[1,2,3,4]" :: [Int]  --[1,2,3,4]  
read "(3, 'a')" :: (Int, Char)  --(3, 'a')  
```

- `Enum` members are sequentially ordered types — they can be enumerated.

```hs
['a'..'e']  --"abcde"  
[LT .. GT]  --[LT,EQ,GT]  
[3 .. 5]    --[3,4,5]  
succ 'B'    --'C' 
```

- `Bounded` members have an upper and a lower bound.

```hs
minBound :: Int   -- -2147483648  
maxBound :: Char  --'\1114111'  
maxBound :: Bool  --True  
minBound :: Bool  --False

:t minBound --(Bounded a) => a

maxBound :: (Bool, Int, Char)  --(True,2147483647,'\1114111')  
```

- `Num` is a numeric typeclass.

```hs
:t 20  --20 :: (Num t) => t  

20 :: Int      --20  
20 :: Integer  --20  
20 :: Float    --20.0  
20 :: Double   --20.0 

:t (*)  --(*) :: (Num a) => a -> a -> a  
```

- `Integral` is also a numeric typeclass for `Int` and `Integer`.
- `Floating` includes only floating point numbers, so `Float` and `Double`.
