


> Written with [StackEdit](https://stackedit.io/).

[TOC]

# Module 1 

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

# < for less than
# > for greater than
# >= for greater than or equal to
# == for equal to each other
# != not equal to each other
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

## Further Readings

+ [Rstudio](http://www.rstudio.com/)
+ [R's history and recent developments](https://www.r-project.org/)
+ [R tutorial](http://www.r-tutor.com/r-introduction/basic-data-types)
+ [R project/ introduction to R](https://cran.r-project.org/doc/manuals/R-intro.pdf)

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

+ Only hold elements of the **same type** (重要的事说两遍^O^ )

+ **Atomic vectors** &lt;against&gt; **lists** (can hold elements of different types)

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

Other wise sum() also can be used in **logical vector**, which will count the number of TRUE in the vector.

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

## Further Readings

+ [r-project/vectors](https://cran.r-project.org/doc/manuals/R-intro.html#Simple-manipulations-numbers-and-vectors)

# Module 3: Matrix

## Create and Name Matrices

### Features

+ Vector: 1D array of data elements

+ Matrix: 2D array of data elements

+ Rows and columns

+ One atomic vector type &lt;against&gt; lists (if we want to **Contain different types**, we need to use **list** or **data.frame**)

### Create a matrix

> **matrix()**

``` r
> matrix(1:6, nrow = 2)
 [,1] [,2] [,3]
 [1,] 1 3 5
 [2,] 2 4 6

> matrix(1:6, ncol = 3)
 [,1] [,2] [,3]
[1,] 1 3 5
[2,] 2 4 6

> matrix(1:6, nrow = 2, byrow = TRUE) # default is FALSE, col by col.
 [,1] [,2] [,3]
[1,] 1 2 3
[2,] 4 5 6
```

> **recycling**

when we pass the matrix function a vector that is **too short to fill up the entire matrix**, recycling activates.
``` r
> matrix(1:3, nrow = 2, ncol = 3)
 [,1] [,2] [,3]
[1,] 1 3 2
[2,] 2 1 3

```

When the matrix with a vector whose multiple does not nicely fit in the matrix.

``` r 
> matrix(1:4, nrow = 2, ncol = 3)
 [,1] [,2] [,3]
[1,] 1 3 1
[2,] 2 4 2
 
# Warning message: In matrix(1:4, nrow = 2, ncol = 3): data length [4] is not a sub-multiple or multiple of the number of columns [3]
```

> **rbind(), cbind()**

Parameters in these two functions are the elements which also follow the recycling rule.

``` r
> cbind(1:3, 1:3) # vevtor order follows by column
 [,1] [,2]
[1,] 1 1
[2,] 2 2
[3,] 3 3

> rbind(1:3, 1:3) # vector order follows by row
 [,1] [,2] [,3]
[1,] 1 2 3
[2,] 1 2 3
```

Combine with **matrix()**

``` r
> m <- matrix(1:6, byrow = TRUE, nrow = 2)

> rbind(m, 7:9)
 [,1] [,2] [,3]
[1,] 1 2 3
[2,] 4 5 6
[3,] 7 8 9

> cbind(m, c(10, 11))
 [,1] [,2] [,3] [,4]
[1,] 1 2 3 10
[2,] 4 5 6 11
```

### Naming a matrix

> **rownames(), colnames()**

``` r
> m <- matrix(1:6, byrow = TRUE, nrow = 2)

> rownames(m) <- c("row1", "row2")
 [,1] [,2] [,3]
row1 1 2 3
row2 4 5 6
> m
 [,1] [,2] [,3]
row1 1 2 3
row2 4 5 6

> colnames(m) <- c("col1", "col2", "col3")
> m
 col1 col2 col3
row1 1 2 3
row2 4 5 6
```

1 line function

``` r
> m <- matrix(1:6, byrow = TRUE, nrow = 2, dimnames = list(c("row1", "row2"), c("col1", "col2", "col3")))

> m
 col1 col2 col3
row1 1 2 3
row2 4 5 6
```

### Coercion

``` r
> num <- matrix(1:8, ncol = 2)
> num
 [,1] [,2]
[1,] 1 5
[2,] 2 6
[3,] 3 7
[4,] 4 8

> char <- matrix(LETTERS[1:6], nrow = 4, ncol = 3)
> char
 [,1] [,2] [,3]
[1,] "A" "E" "C"
[2,] "B" "F" "D"
[3,] "C" "A" "E"
[4,] "D" "B" "F" 

> num <- matrix(1:8, ncol = 2)
> char <- matrix(LETTERS[1:6], nrow = 4, ncol = 3)
> cbind(num, char)
 [,1] [,2] [,3] [,4] [,5]
[1,] "1" "5" "A" "E" "C"
[2,] "2" "6" "B" "F" "D"
[3,] "3" "7" "C" "A" "E"
[4,] "4" "8" "D" "B" "F"
```


## Subsetting Matrices

### Subset element

``` r
> m <- matrix(sample(1:15, 12), nrow = 3)
> m
 [,1] [,2] [,3] [,4]
[1,] 5 11 15 3
[2,] 12 14 8 9
[3,] 6 1 4 2

> m[1,3]
[1] 15 # Generate a 1-dimensional vector

> m[3,2]
[1] 1
```

### Subset column or row

``` r
> m
 [,1] [,2] [,3] [,4]
[1,] 5 11 15 3
[2,] 12 14 8 9
[3,] 6 1 4 2

> m[3,] # select the 3th row as a vector.
[1] 6 1 4 2

> m[,3] # select the 3th column as a vector.
[1] 15 8 4

> m[4] # select the 4th element. The elements selection order is column by column
[1] 11

> m[9]
[1] 4
```

### Subset multiple elements

we can't select elements that don't have **one of row or column index** in common. If you want to select the 11, on row 1 and column 2, and 8, on row 2 and column 3, this call will not give the wanted result. Instead, R will return a **sub-matrix**.
``` r
> m
 [,1] [,2] [,3] [,4]
[1,] 5 11 15 3
[2,] 12 14 8 9
[3,] 6 1 4 2

> m[2, c(2, 3)] # construct a selection vector. The same as vector subset, the selection vector order will decide the result order. 
[1] 14 8

> m[c(1, 2), c(2, 3)]
 [,1] [,2]
[1,] 11 15
[2,] 14 8

> m[c(1, 3), c(1, 3, 4)]
 [,1] [,2] [,3]
[1,] 5 15 3
[2,] 6 4 2
```

### Subset by name

``` r
> rownames(m) <- c("r1", "r2", "r3")
> colnames(m) <- c("a", "b", "c", "d")
> m
 a b c d
r1 5 11 15 3
r2 12 14 8 9
r3 6 1 4 2

> m[2,3]
[1] 8

> m["r2","c"] # unlike vector, double quote in matrix is necessary.
[1] 8
```

mix up names and number
``` r
> m[2,"c"]
[1] 8

> m[3, c("c", "d")]
c d
4 2
```

### Subset with logical vector

``` r
> m
 a b c d
r1 5 11 15 3
r2 12 14 8 9
r3 6 1 4 2

> m[c(FALSE, FALSE, TRUE),
 c(FALSE, FALSE, TRUE, TRUE)]
c d
4 2

> m[c(FALSE, FALSE, TRUE),
 c(FALSE, TRUE)] # recycling
b d
1 2

> m[c(FALSE, FALSE, TRUE),
 c(FALSE, TRUE, FALSE, TRUE)]
b d
1 2
```

## Matrix Calculus

### Matrix Calculus

+ Matrix special functions: colSums(), rowSums()

+ Like vector, matrix can manipulate standard arithmetic possible.

+ **Element-wise** computation

### Example: lotr_matrix

``` r
> the_fellowship <- c(316, 556)
> two_towers <- c(343, 584)
> return_king <- c(378, 742)

> lotr_matrix <- rbind(the_fellowship, two_towers, return_king)
> colnames(lotr_matrix) <- c("US", "non-US")
> rownames(lotr_matrix) <- c("Fellowship", "Two Towers",
 "Return King")

> lotr_matrix
 US non-US
Fellowship 316 556
Two Towers 343 584
Return King 378 742

> lotr_matrix
 US non-US
Fellowship 316 556
Two Towers 343 584
Return King 378 742
```

### Matrix - Scalar Calculus

``` r
> lotr_matrix
 US non-US
Fellowship 316 556
Two Towers 343 584
Return King 378 742

> lotr_matrix / 1.12 # element-wise
 US non-US
Fellowship 282.1429 496.4286
Two Towers 306.2500 521.4286
Return King 337.5000 662.5000

> lotr_matrix - 50 # element-wise
 US non-US
Fellowship 266 506
Two Towers 293 534
Return King 328 692
```

### Matrix - Matrix Calculus

``` r
> lotr_matrix
 US non-US
Fellowship 316 556
Two Towers 343 584
Return King 378 742

> # Definition of theater_cut omitted
> theater_cut
 [,1] [,2]
[1,] 50 50
[2,] 80 80
[3,] 100 100

> lotr_matrix - theater_cut
 US non-US
Fellowship 266 506
Two Towers 263 504
Return King 278 642
```

### Matrix Calculus



``` r
> lotr_matrix
 US non-US
Fellowship 316 556
Two Towers 343 584
Return King 378 742

> lotr_matrix - c(50, 80, 100) # R will perform recycling. The vector is extended to a matrix of the same size, and is filled up with the vector elements column by column.
 US non-US
Fellowship 266 506
Two Towers 263 504
Return King 278 642

> matrix(c(50, 80, 100), nrow = 3, ncol = 2) # The matrix that is thus actually subtracted from the lotr matrix
 [,1] [,2]
[1,] 50 50
[2,] 80 80
[3,] 100 100
```

### Matrix Multiplication

This is not the matrix in math definition which shoud use `%*%`. Thus its operation is just like vector.

``` r
> lotr_matrix
 US non-US
Fellowship 316 556
Two Towers 343 584
Return King 378 742

> # Definition of rates omitted
> rates
 [,1] [,2]
[1,] 1.11 1.11
[2,] 0.99 0.99
[3,] 0.82 0.82

> lotr_matrix * rates
 US non-US
Fellowship 350.76 617.16
Two Towers 339.57 578.16
Return King 309.96 608.44
```

### Matrices and Vectors

Very similar
 : simply are data structures that can store elements of the same type
 <br>

Vector = 1D, matrix = 2D
 : The vector does this in a one-dimensional sequence, while the matrix uses a two-dimensional grid structure.
<br>

Coercion if necessary
: when you want to store elements of different types.
<br>

Recycling if necessary
: col by col.
<br>

Element-wise calculus
: Calculus are **straightforward**, all calculus is performed element-wise.

## Further reading

+ [r-project/matrices](https://cran.r-project.org/doc/manuals/R-intro.html#Arrays-and-matrices): it also contains more advanced operations on matrices, like how to take the determinant of a matrix in R or how to transpose a matrix

+ [ats.ucla.edu/matrices](http://www.ats.ucla.edu/stat/r/library/matrix_alg.htm): Here the concept of working with matrices in R is once again explained and some more technical examples are also discussed

# Module 4: Factors

## Factors

### Categorical Variables

+ Limited number of different values

+ Belong to category (ordered or non-ordered)

+ In R: factor (a data structure to save categorical variables)

### Create a factor

> **matrix()**

**An example: blood type.**

``` r
> blood <- c("B", "AB", "O", "A", "O", "O", "A", "B")
> blood
[1] "B" "AB" "O" "A" "O" "O" "A" "B"
factor()

> blood_factor <- factor(blood) # create a factor
> blood_factor
[1] B AB O A O O A B
Levels: A AB B O # auto levels. R sorts levels alphabetically.
> str(blood_factor) # inspect the factor.
 Factor w/ 4 levels "A","AB","B","O": 3 2 4 1 4 4 1 3
```

when we call the factor function, R basically does 2 things.

1. It **scans through** the vector to see the **different categories** that are in there and sorts levels **alphabetically**.

2. it converts the character vector, blood in this example, to a vector of **integer values**. These integers correspond to a set of character values to use when the factor is displayed.

Thus, factors are actually **integer vectors**, where each integer corresponds to a category, or a level.

### Order levels differently

> **levels = c(...)**
``` r
> blood_factor2 <- factor(blood,
 levels = c("O", "A", "B", "AB"))
> blood_factor2
[1] B AB O A O O A B
Levels: O A B AB

> str(blood_factor2)
 Factor w/ 4 levels "O","A","B","AB": 3 4 1 2 1 1 2 3

> str(blood_factor)
 Factor w/ 4 levels "A","AB","B","O": 3 2 4 1 4 4 1 3
```

### Rename factor levels

> **levels(raw factor) <- c(...)**
>
> **labels = ...**

``` r
> blood <- c("B", "AB", "O", "A", "O", "O", "A", "B")
> blood_factor <- factor(blood)
> levels(blood_factor) <- c("BT_A", "BT_AB", "BT_B", "BT_O")
> blood_factor
[1] BT_B BT_AB BT_O BT_A BT_O BT_O BT_A BT_B
Levels: BT_A BT_AB BT_B BT_O

> factor(blood, labels = c("BT_A", "BT_AB", "BT_B", "BT_O"))
[1] BT_B BT_AB BT_O BT_A BT_O BT_O BT_A BT_B
Levels: BT_A BT_AB BT_B BT_O
```

Sometimes it's a bit **confusing**. For both of these approaches, it's important to follow **the same order as the order of the factor levels**: first A, then AB, then B and then O.

Thus, to solve it:

> combination of manually specifying the `levels` and the `labels`
argument

``` r
> factor(blood,
 levels = c("O", "A", "B", "AB"),
 labels = c("BT_O", "BT_A", "BT_B", "BT_AB"))
[1] BT_B BT_AB BT_O BT_A BT_O BT_O BT_A BT_B
Levels: BT_O BT_A BT_B BT_AB

# not only specify the order, just like before, while with the labels, we specify a new name for the categories as well.
```

### Nominal Variables versus Ordinal Variables

**An example: T shirt size VS blood type.**

> **ordered = c(...)**: the ordinal order follows the writing order.

``` r
> blood <- c("B", "AB", "O", "A", "O", "O", "A", "B")
> blood_factor <- factor(blood)
> blood_factor[1] < blood_factor[2]
[1] NA
Warning message:
In Ops.factor(blood_factor[1], blood_factor[2]) :
 ‘<’ not meaningful for factors

> tshirt <- c("M", "L", "S", "S", "L", "M", "L", "M")
> tshirt_factor <- factor(tshirt, ordered = TRUE,
 levels = c("S", "M", "L"))
> tshirt_factor
[1] M L S S L M L M
Levels: S < M < L
```

### Ordered factor

``` r
> tshirt <- c("M", "L", "S", "S", "L", "M", "L", "M")
> tshirt_factor <- factor(tshirt, ordered = TRUE,
 levels = c("S", "M", "L"))

> tshirt_factor
[1] M L S S L M L M
Levels: S < M < L

> tshirt_factor[1] < tshirt_factor[2]
[1] TRUE
```

### Wrap-up

+ Factors for storing categorical variables

+ Factors are integer vectors

+ Change factor levels: levels() function or labels argument

+ Ordered factors: ordered = TRUE. Catering to both nominal and ordinal variables

### Extra knowledge from labs

[summary()](http://www.rdocumentation.org/packages/base/functions/summary)
: This function could produce result summaries of the results of various model fitting functions.
 > ``` r
 > # Defintion of survey_vector and survey_factor
 > survey_vector <- c("R", "L", "L", "R", "R")
 > survey_factor <- factor(survey_vector, levels = c("R", "L"), labels = c("Right", "Left"))
 >
 > # Summarize survey_vector
 > summary(survey_vector)
 > Length     Class      Mode 
 >     5 character character 
 >
 > # Summarize survey_factor
 > summary(survey_factor)
 >Right  Left 
 >3        2
 >```

## Further Readings

+ [r-project/factors](https://cran.r-project.org/doc/manuals/R-intro.html#Factors)

+ [stat.ethz.chse/factors](https://stat.ethz.ch/R-manual/R-devel/library/base/html/factor.html)

# Module 5: Lists

## Create and name lists

### Features

+ Vector: 1D, same type

+ Matrix: 2D, same type

+ List
 - Could store different R objects(vectors, matrices, dates, data frames, factors and many more)
 - No coercion
 - Loss of some functionality that vectors and matrices offered
 - calculus with lists is far less straightforward due to the lack of predefined structure that lists have to follow.

### Create list

> **list()**

``` r
> c("Rsome times", 190, 5)

> list("Rsome times", 190, 5)
[[1]]
[1] "Rsome times"
[[2]]
[1] 190
[[3]]
[1] 5
[1] "Rsome times" "190" "5"

> song <- list("Rsome times", 190, 5)
> is.list(song)
[1] TRUE
```

### Name list

``` r
> song <- list("Rsome times", 190, 5)
> names(song) <- c("title", "duration", "track")

> song
$title # the indices in double square brackets have changed to the names of the list elements 
[1] "Rsome times"
$duration
[1] 190
$track
[1] 5
```

One-line approach

> **list(name = value...)**
``` r
> song <- list(title = "Rsome times",
 duration = 190,
 track = 5)
```

Better way to print list

> **str()**

``` r
> str(song)
List of 3
 $ title : chr "Rsome times"
 $ duration: num 190
 $ track : num 5
```

### List in List

``` r
> similar_song <- list(title = "R you on time?",
 duration = 230)
> song <- list(title = "Rsome times",
 duration = 190, track = 5,
 similar = similar_song) # list in list

> str(song)
List of 4
 $ title : chr "Rsome times"
 $ duration: num 190
 $ track : num 5
 $ similar :List of 2
 ..$ title : chr "R you on time?"
 ..$ duration: num 230
```

## Subset and Extend Lists

Note, the printout of list is given by `str()` function.

### `[` versus `[[`

An example: the song list

``` r
> similar_song <- list(title = "R you on time?",
 duration = 230)
> song <- list(title = "Rsome times",
 duration = 190, track = 5,
 similar = similar_song)

> song
List of 4
 $ title : chr "Rsome times"
 $ duration: num 190
 $ track : num 5
 $ similar :List of 2
 ..$ title : chr "R you on time?"
 ..$ duration: num 230
```


> `[` returns to a list
> 
> `[[` returns to the value

``` r
> song[1]
List of 1
 $ title: chr "Rsome times"

> song[[1]]
[1] "Rsome times"

> song[c(1, 3)] # also returns a list
List of 2
 $ title: chr "Rsome times"
 $ track: num 5
```

A `[[` Error

``` r
> song[[c(1, 3)]] # double brackets are only to select single elements from a list.
Error in song[[c(1, 3)]] :
 subscript out of bounds

> song[[1]][[3]] #  take the first element from the song list, and from that list, take the third element.
Error in song[[1]][[3]] :
 subscript out of bounds
# tip: above two are equal expressions.

# Thus

> song[[4]][[1]]
[1] "R you on time?"

> song[[c(4, 1)]]
[1] "R you on time?"
```

The double brackets are **only to select single elements** from a list.

### Subset by names

``` r
> song[["duration"]] # with double quotes
[1] 190

> song["duration"] # select a list
List of 1
 $ duration: num 190

> song[c("duration", "similar")] # select several lists
List of 2
 $ duration: num 190
 $ similar :List of 2
 ..$ title : chr "R you on time?"
 ..$ duration: num 230
```

### Subset by logicals

``` r
> song[c(FALSE, TRUE, TRUE, FALSE)]
List of 2
 $ duration: num 190
 $ track : num 5

> song[[c(FALSE, TRUE, TRUE, FALSE)]] # which throws a error because R can't recognize the expression.
Error : attempt to select less than one element

> song[[F]][[T]][[T]][[F]]
Error : attempt to select less than one element
```

### $ and extending

It works just the same as the double brackets but **only works on named** lists.

``` r
# select a element
> song$duration
[1] 190

# add a new element
> friends <- c("Kurt", "Florence",
 "Patti", "Dave")
> song$sent <- friends

> song
List of 5
 $ title : chr "Rsome times"
 $ duration: num 190
 $ track : num 5
 $ similar :List of 2
 ..$ title : chr "R you on time?"
 ..$ duration: num 230
 $ sent : chr [1:4] "Kurt" "Florence" "Patti" "Dave"

> song[["sent"]] <- friends # This is another way to add new elements
```

Add elements to embedded lists.

``` r
> song$similar$reason <- "too long"
> song
List of 5
 $ title : chr "Rsome times"
 $ duration: num 190
 $ track : num 5
 $ similar :List of 3
 ..$ title : chr "R you on time?"
 ..$ duration: num 230
 ..$ reason : chr "too long" # new element in the embedded list
 $ sent : chr [1:4] "Kurt" "Florence" "Patti" "Dave"
``` 

### Wrap-up

+ `[[` or `[` ?
 - `[[` to select list element
 - `[` results in sublist

+ `[[` and `$` to subset and extend lists

## Extra knowledge from lab

c()

: We can even use the c() function to add an element
> shining_list <- c(shining_list, my_opinion = "Love it!")

vector in list

: if we want to add an entire vector as an element to the list
> shining_list_ext <- c(shining_list, opinions = c("Love it!", "Hate it!"))
: This will return 
 ``` r
 > shining_list_ext
 $title
 [1] "The Shining"

 $actors
 [1] "Jack Nicholson"   "Shelley Duvall"   "Danny Lloyd"      "Scatman   Crothers"
 [5] "Barry Nelson"    

 $reviews
 [1] Good    OK      Good    Perfect Bad     Perfect Good   
 Levels: Bad < OK < Good < Perfect

 $opinions1
 [1] "Love it!"

 $opinions2
 [1] "Hate it!"
 ```

: Thus, we'd better surround the elements you want to add to the list in another list() function. 

 ``` r
 c(shining_list, 
     list(my_opinion = "Love it!",
       your_opinion = "Hate it!"))

 c(shining_list, 
     list(c("Love it!", "Hate it"!)))
 ```


## Further readings

+ [r-project.org/Lists](https://cran.r-project.org/doc/manuals/R-intro.html#Lists)

+ [R-tutorials/List](http://www.r-tutor.com/r-introduction/list)

# Module 6: Data Frame

## Explore the Data Frame

### Datasets

+ Observation

+ Variables

+ Emample: Datasets

 - each person = **observation**
 - properties (name, age …) = **variables **
 
         |name|age|child|
         |--|--|--|
         |Pete|30|TRUE|
         |Frank|21|TRUE|
         |Hehe|25|TRUE|
             
+ Matrix? Need different types

+ List? Not very practical

### Data Frame

+ Specifically for datasets

+ **Rows = observations** (persons)

+ **Columns = variables** (age, name, …)

+ Contain **elements of different types**

+ Elements in **same column**: same type

### Create Data Frame

Usually, we don't need create data frame manually.

+ Import from data source

+ CSV file

+ Relational Database (e.g. SQL)

+ Software packages (Excel, SPSS …)

### Create Data Frame Manually

> **data.frame()**

``` r
> name <- c("Anne", "Pete", "Frank", "Julia", "Cath")
> age <- c(28, 30, 21, 39, 35)
> child <- c(FALSE, TRUE, TRUE, FALSE, TRUE)
> df <- data.frame(name, age, child)

> df
 name age child # column names match variable names
1 Anne 28 FALSE
2 Pete 30 TRUE
3 Frank 21 TRUE
4 Julia 39 FALSE
5 Cath 35 TRUE
```

### Name Data Frame

``` r
> names(df) <- c("Name", "Age", "Child") # names() function
> df
 Name Age Child
1 Anne 28 FALSE
2 Pete 30 TRUE
 ...
5 Cath 35 TRUE

> df <- data.frame(Name = name, Age = age, Child = child) # inline-name
> df
 Name Age Child
1 Anne 28 FALSE
2 Pete 30 TRUE
 ...
5 Cath 35 TRUE
```

Like in matrices, it's also possible to **name the rows of the data frame**, but that's generally **not a good idea**.

### Data Frame Structure

+ Data frame is **actually a list** containing all vectors of the same length.

+ Strings & factor coercion.

> **stringsAsFactors = FALSE**

``` r
> str(df)
'data.frame': 5 obs. of 3 variables:
 $ Name : Factor w/ 5 levels "Anne","Cath",..: 1 5 3 4 2 # Factor instead of character
 $ Age : num 28 30 21 39 35
 $ Child: logi FALSE TRUE TRUE FALSE TRUE

> data.frame(name[-1], age, child)
Error : arguments imply differing number of rows: 4, 5

> df <- data.frame(name, age, child,
 stringsAsFactors = FALSE)

> str(df)
'data.frame': 5 obs. of 3 variables:
 $ name : chr "Anne" "Pete" "Frank" "Julia" ...
 $ age : num 28 30 21 39 35
 $ child: logi FALSE TRUE TRUE FALSE TRUE
```

A requirement that is not present for lists is that **the length of the vectors you put** in the list **has to be equal**.

## Subset - Extend - Sort Data Frames

### Subset Data Frame

+ Subsetting syntax from matrices and lists

+ [ from matrices

+ [[ and $ from lists

### Example: people

``` r
> name <- c("Anne", "Pete", "Frank", "Julia", "Cath")
> age <- c(28, 30, 21, 39, 35)
> child <- c(FALSE, TRUE, TRUE, FALSE, TRUE)
> people <- data.frame(name, age, child,
 stringsAsFactors = FALSE)

> people
 name age child
1 Anne 28 FALSE
2 Pete 30 TRUE
3 Frank 21 TRUE
4 Julia 39 FALSE
5 Cath 35 TRUE
```