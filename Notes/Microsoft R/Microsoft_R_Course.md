


> Written with [StackEdit](https://stackedit.io/).

# Module 0 

## The True Basics

### Variable

> **<-**: define a variable

``` r
a <- 15
```

### Basic Calculation

> \+
> \-
> *
> /
> ^
> %%

### Workspace

> **ls()**: Chekc the work space
> **rm()**: Delete variables in the workspace

``` r
# clear the workspace
rm(list = ls())
```

## Basic Data Types

### Check the type

> **class()** # Output is the name of type
>
>**is.\*\*()** # Output is logical judgement

### Coercion to Convert The Type

> **as.\*\*()**

### Logical

``` r
TRUE

FALSE

T

F

NA
```

### Numeric

``` r
4.5
5
```
**integer** belongs to numeric

``` r
5L # 5

12L # 12

class(12L) # "integer"

class(12.5L) # "numerical" -> 12.5

```

### Character

``` r
"Hello world!"
```

## Reading

+ [Rstudio](http://www.rstudio.com/)
+ [R's history and recent developments](https://www.r-project.org/)
+ [R tutorial](http://www.r-tutor.com/r-introduction/basic-data-types)

---

# Module 2

## Create And Name Vectors

### Vector

+ **Sequence** of data elements 

+ With **Same** basic type

+ **One dimensional arrays** that can hold **numeric data, character data, or logical data**

### Create a vector

> **c( )**

``` r
> c("hearts", "spades", "diamonds", "diamonds", "spades")
[1] "hearts" "spades" "diamonds" "diamonds" "spades"

> drawn_suits <- c("hearts", "spades", "diamonds",
 "diamonds", "spades")
 
> drawn_suits
[1] "hearts" "spades" "diamonds" "diamonds" "spades"

> is.vector(drawn_suits)
[1] TRUE
```

### Name a vector

> **names( )** 

``` r
> remain <- c(11, 12, 11, 13)
> remain
[1] 11 12 11 13

> suits <- c("spades", "hearts", "diamonds", "clubs")

# names(raw vector) <- name vector
> names(remain) <- suits # names a vector
> remain
[1]spades hearts diamonds clubs
       11     12       11    13

> remain <- c(spades = 11, hearts = 12,
 diamonds = 11, clubs = 13) # 2nd way to name a vector
 
> remain <- c("spades" = 11, "hearts" = 12,
 "diamonds" = 11, "clubs" = 13) # 3rd way to name a vector. naming without double quote is OK.

> str(remain) # use str() function to name a vector
 Named num [1:4] 11 12 11 13
 - attr(*, "names")= chr [1:4] "spades" "hearts"
 "diamonds" "clubs"
```

### Single value = vector

 R does not provide a **data structure** to hold a single number or a single character string or any other basic data type: they're all
just vectors of **length 1**.

``` r
> my_apples <- 5
> my_oranges <- "six"

> is.vector(my_apples)
[1] TRUE

> is.vector(my_oranges)
[1] TRUE

> length(my_apples)
[1] 1

> length(my_oranges)
[1] 1

> length(drawn_suits)
[1] 5
```

### Vectors are homogeneous

+ Only elements of the **same type** (重要的事说两遍^O^ )

+ **Atomic vectors** &lt;against&gt; **lists** 

+ Automatic coercion if necessary

 -  R **automatically performs coercion** to make sure that you end up with a vector that contains elements of the same type if the basic data type in c() contrast.
 ``` r
 > drawn_ranks <- c(7, 4, "A", 10, "K", 3, 2, "Q")
> drawn_ranks
[1] "7" "4" "A" "10" "K" "3" "2" "Q"
> class(drawn_ranks)
[1] "character"
 ```

 -  'Upgrading' **logicals to numerics**, **logicals to characters**and **numerics to characters** when necessary.

## Vector Calculus

``` r
> my_apples <- 5 # my_apples is a vector!
> my_oranges <- 6 # my_oranges is a vector!
> my_apples + my_oranges
[1] 11
```

### Element-wise

``` r
> earnings <- c(50, 100, 30)
> earnings * 3
[1] 150 300 90
```

Mathematics naturally extend.

``` r
> earnings/10
[1] 5 10 3

> earnings - 20
[1] 30 80 10

> earnings + 100
[1] 150 200 130

> earnings^2
[1] 2500 10000 900
```

**multiplication and division** are done element-wise!

``` r
> earnings <- c(50, 100, 30)
> expenses <- c(30, 40, 80)
> earnings - expenses
[1] 20 60 -50

> earnings + c(10, 20, 30)
[1] 60 120 60

> earnings * c(1, 2, 3)
[1] 50 200 90

> earnings / c(1, 2, 3)
[1] 50 50 10
```

### sum() and &gt;

``` r
> earnings <- c(50, 100, 30)
> expenses <- c(30, 40, 80)
> bank <- earnings - expenses
> bank
[1] 20 60 -50

> sum(bank)
[1] 30

> earnings > expenses
[1] TRUE TRUE FALSE
```

## Vector subsetting

### Subset by index

``` r
> remain <- c(spades = 11, hearts = 12,
 diamonds = 11, clubs = 13)
> remain[1]  # [1] -> take element at index 1 result is a (named) vector too!
spades
    11
> remain[3]
diamonds
      11
```

### Subset by name

``` r
> remain <- c(spades = 11, hearts = 12,
 diamonds = 11, clubs = 13)
> remain["spades"]
spades
    11

> remain["diamonds"]
diamonds
      11
```

### Subset multiple elements

``` r
> remain <- c(spades = 11, hearts = 12,
 diamonds = 11, clubs = 13)
> remain_black <- remain[c(1, 4)]
> remain_black
spades clubs
    11    13
 
> remain[c(4, 1)] # resulting vector is ordered depends on the order of the indices inside the selection
 clubs spades
    13    11
 
> remain[c("clubs", "spades")]
 clubs spades
    13     11 
```

### Subset all but some

``` r
> remain <- c(spades = 11, hearts = 12,
 diamonds = 11, clubs = 13)

> remain[-1] # All but index 1 are returned
 hearts diamonds clubs
     12       11    13

> remain[-c(1, 2)]
diamonds clubs
      11    13

> remain[-"spades"]
Error in -"spades" : invalid argument to unary operator
```

### Subset using logical vector

``` r
> remain <- c(spades = 11, hearts = 12,
 diamonds = 11, clubs = 13)
> remain[c(FALSE, TRUE, FALSE, TRUE)]
hearts clubs
    12    13
 
> selection_vector <- c(FALSE, TRUE, FALSE, TRUE)
> remain[selection_vector]
hearts clubs
     12    13 
```

R is smart enough to see that the vector of logicals you passed it is shorter than the `remain` vector, so it **repeats the contents of the vector** until it has the same length as `remain`, so called **"recycling"**.

``` r
> remain <- c(spades = 11, hearts = 12,
 diamonds = 11, clubs = 13)
> remain[c(TRUE, FALSE)]
 spades diamonds
     11       11

> remain[c(TRUE, FALSE, TRUE, FALSE)]
 spades diamonds
     11       11

> remain[c(TRUE, FALSE, TRUE)]
 spades diamonds clubs
     11       11    13

> remain[c(TRUE, FALSE, TRUE, TRUE)]
 spades diamonds clubs
     11       11    13 
```

## Further reading

+ [r-project/vectors](https://cran.r-project.org/doc/manuals/R-intro.pdf)
