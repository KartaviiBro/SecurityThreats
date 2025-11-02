# Lab1

## Цель

1) Развить практические навыки использования языка программирования R для обработки данных
2) Развить навыки работы в Rstudio IDE
3) Закрепить знания базовых типов данных языка R и простейших операций с ними

## Исходные данные

1) Windows 11
2) Rstudio
3) Github

## План

1) Установить программный пакет swirl
2) Запустить задание с помощью swirl::swirl()
3) Выбрать из меню курсов 1. R Programming: The basics of programming in R
4) Составить отчет и выложить его и исходный qmd/rmd файл в свой репозиторий

### Шаг 1. Установка программного пакет swirl.


### Шаг 2. Запуск swirl и выбор обучения


### Шаг 3. Выполнение курсов

-   базовые структурные блоки (Basic Building Blocks)

```{r}
5 + 7
```

```{r}
[1] 12
```

```{r}
x <- 5 + 7
```

```{r}
x
```

```{r}
[1] 12
```

```{r}
y <- x - 3
```

```{r}
y
```

```{r}
[1] 9
```

```{r}
z <- c(1.1, 9, 3.14)
```

```{r}
?c
```

```{r}
запускаю httpd сервер помощи... готово
```

```{r}
z
```

```{r}
[1] 1.10 9.00 3.14
```

```{r}
c(z,555, z)
```

```{r}
[1]   1.10   9.00   3.14 555.00   1.10   9.00   3.14
```

```{r}
z * 2 + 100
```

```{r}
[1] 102.20 118.00 106.28
```

```{r}
my_sqrt <- sqrt(z - 1)
```

```{r}
my_sqrt
```

```{r}
[1] 0.3162278 2.8284271 1.4628739
```

```{r}
 my_div <- z / my_sqrt
```

```{r}
my_div
```

```{r}
[1] 3.478505 3.181981 2.146460
```

```{r}
c(1, 2, 3, 4) + c(0, 10)
```

```{r}
[1]  1 12  3 14
```

```{r}
c(1, 2, 3, 4) + c(0, 10, 100)
```

```{r}
[1]   1  12 103   4
Предупреждение:
В c(1, 2, 3, 4) + c(0, 10, 100) :
  длина большего объекта не является произведением длины меньшего объекта
```

```{r}
z * 2 + 1000
```

```{r}
[1] 1002.20 1018.00 1006.28
```

```{r}
my_div
```

```{r}
[1] 3.478505 3.181981 2.146460
```

-   рабочие пространства и файлы (Workspace and Files)

```{r}
getwd()
```

```{r}
[1] "C:/Users/Ivan/Documents/SecurityThreats/1"
```

```{r}
ls()
```

```{r}
[1] "my_div"  "my_sqrt" "x"       "y"       "z"       "z2"    
```

```{r}
x <- 9
```

```{r}
ls()
```

```{r}
[1] "my_div"  "my_sqrt" "x"       "y"       "z"       "z2" 
```

```{r}
dir()
```

```{r}
[1] "1.Rproj"
```

```{r}
?list.files
```

```{r}
args(list.files)
```

```{r}
function (path = ".", pattern = NULL, all.files = FALSE, full.names = FALSE, 
    recursive = FALSE, ignore.case = FALSE, include.dirs = FALSE, 
    no.. = FALSE) 
NULL
```

```{r}
old.dir <- getwd()
```

```{r}
dir.create("testdir")
```

```{r}
setwd("testdir")
```

```{r}
file.create("mytest.R")
```

```{r}
[1] TRUE
```

```{r}
ls()
```

```{r}
[1] "my_div"  "my_sqrt" "old.dir" "x"       "y"       "z"       "z2"     
```

```{r}
list.files()
```

```{r}
[1] "mytest.R"
```

```{r}
file.exists("mytest.R")
```

```{r}
[1] TRUE
```

```{r}
file.info("mytest.R")
```

```{r}
 size isdir mode               mtime               ctime               atime exe
mytest.R    0 FALSE  666 2024-11-29 20:33:12 2024-11-29 20:33:12 2024-11-29 20:33:12  no
```

```{r}
file.rename("mytest.R", "mytest2.R")
```

```{r}
[1] TRUE
```

```{r}
file.copy("mytest2.R", "mytest3.R")
```

```{r}
[1] TRUE
```

```{r}
file.path("mytest3.R")
```

```{r}
[1] "mytest3.R"
```

```{r}
file.path("folder1", "folder2")
```

```{r}
[1] "folder1/folder2"
```

```{r}
?dir.create
```

```{r}
dir.create(file.path('testdir2', 'testdir3'), recursive = TRUE)
```

```{r}
unlink('testdir2', recursive = TRUE)
```

```{r}
setwd(old.dir)
```

-   последовательности чисел (Sequences of Numbers)

```{r}
1:20
```

```{r}
[1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20
```

```{r}
pi:10
```

```{r}
[1] 3.141593 4.141593 5.141593 6.141593 7.141593 8.141593 9.141593
```

```{r}
15:1
```

```{r}
[1] 15 14 13 12 11 10  9  8  7  6  5  4  3  2  1
```

```{r}
?':'
```

```{r}
seq(1,20)
```

```{r}
[1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20
```

```{r}
seq(0, 10, by=0.5)
```

```{r}
[1]  0.0  0.5  1.0  1.5  2.0  2.5  3.0  3.5  4.0  4.5  5.0  5.5  6.0  6.5  7.0  7.5  8.0  8.5  9.0  9.5 10.0
```

```{r}
my_seq <- seq(5, 10, length=30)
```

```{r}
length(my_seq)
```

```{r}
[1] 30
```

```{r}
1:length(my_seq)
```

```{r}
[1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30
```

```{r}
seq(along.with = my_seq)
```

```{r}
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30
```

```{r}
seq_along(my_seq)
```

```{r}
[1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30
```

```{r}
rep(0, times=40)
```

```{r}
 [1] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
```

```{r}
rep(c(0, 1, 2), times = 10)
```

```{r}
[1] 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2
```

```{r}
rep(c(0, 1, 2), each = 10)
```

```{r}
[1] 0 0 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1 1 1 2 2 2 2 2 2 2 2 2 2
```

-   векторы (Vectors)

```{r}
num_vect <- c(0.5, 55, -10, 6)
```

```{r}
tf <- (num_vect < 1)
```

```{r}
tf <- num_vect < 1
```

```{r}
tf
```

```{r}
[1]  TRUE FALSE  TRUE FALSE
```

```{r}
num_vect >= 6
```

```{r}
[1] FALSE  TRUE FALSE  TRUE
```

```{r}
my_char <- c("My", "name", "is")
```

```{r}
my_char
```

```{r}
[1] "My"   "name" "is"  
```

```{r}
paste(my_char, collapse = " ")
```

```{r}
[1] "My name is"
```

```{r}
my_name <- c(my_char, "Johnny")
```

```{r}
my_name
```

```{r}
[1] "My"     "name"   "is"     "Johnny"
```

```{r}
paste(my_name, collapse = " ")
```

```{r}
[1] "My name is Johnny"
```

```{r}
paste("Hello", "world!", sep = " ")
```

```{r}
[1] "Hello world!"
```

```{r}
paste(1:3, c("X", "Y", "Z"), sep = "")
```

```{r}
[1] "1X" "2Y" "3Z"
```

```{r}
paste(LETTERS, 1:4, sep = "-")
```

```{r}
[1] "A-1" "B-2" "C-3" "D-4" "E-1" "F-2" "G-3" "H-4" "I-1" "J-2" "K-3" "L-4" "M-1" "N-2" "O-3" "P-4" "Q-1" "R-2" "S-3"
[20] "T-4" "U-1" "V-2" "W-3" "X-4" "Y-1" "Z-2"
```

-   пропущенные значения (Missing Values)

```{r}
x <- c(44, NA, 5, NA)
```

```{r}
x * 3
```

```{r}
[1] 132  NA  15  NA
```

```{r}
y <- rnorm(1000)
```

```{r}
 z <- rep(NA, 1000)
```

```{r}
my_data <- sample(c(y, z), 100)
```

```{r}
my_na <- is.na(my_data)
```

```{r}
my_na
```

```{r}
  [1] FALSE FALSE FALSE  TRUE  TRUE FALSE  TRUE  TRUE  TRUE FALSE FALSE  TRUE  TRUE  TRUE  TRUE FALSE  TRUE FALSE  TRUE
 [20]  TRUE FALSE  TRUE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE
 [39]  TRUE FALSE FALSE  TRUE FALSE  TRUE  TRUE FALSE  TRUE  TRUE FALSE FALSE  TRUE FALSE  TRUE FALSE  TRUE FALSE FALSE
 [58] FALSE FALSE  TRUE FALSE  TRUE  TRUE FALSE  TRUE FALSE  TRUE FALSE  TRUE  TRUE  TRUE FALSE FALSE FALSE  TRUE  TRUE
 [77] FALSE  TRUE FALSE FALSE  TRUE FALSE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE FALSE FALSE FALSE
 [96] FALSE FALSE FALSE FALSE FALSE
```

```{r}
my_data == NA
```

```{r}
  [1] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
 [39] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
 [77] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
```

```{r}
sum(my_na)
```

```{r}
[1] 43
```

```{r}
my_data
```

```{r}
  [1]  0.08362896 -0.28306636 -0.47190571          NA          NA -3.03837811          NA          NA          NA
 [10]  0.28117647  2.08111608          NA          NA          NA          NA -0.12018628          NA -0.73127944
 [19]          NA          NA  0.92748941          NA -0.39861981  0.97889912          NA  0.21774845 -0.84545576
 [28]  0.86326550 -2.90609642          NA          NA  0.41579239  0.66792882  0.64363934 -0.73601650  0.20161431
 [37]          NA -0.64467223          NA  1.77419527 -1.44624006          NA  1.44432340          NA          NA
 [46]  0.04951320          NA          NA  1.94737971 -0.70272302          NA  0.38711052          NA -1.03858900
 [55]          NA  0.44835815 -0.37145023 -1.01057626 -0.19117600          NA -1.01672333          NA          NA
 [64] -0.96833865          NA -0.27783598          NA -0.39356156          NA          NA          NA -0.71422726
 [73] -1.21380852  1.75317157          NA          NA -0.60118119          NA  0.91580136 -0.04115045          NA
 [82] -0.59016544          NA          NA -0.93612995 -1.25837814  0.01825490  0.67913210 -1.37292324          NA
 [91]          NA          NA  0.45014625 -1.56344616  0.33512269  0.39557612 -0.24868239 -0.29508334 -0.41771445
```

```{r}
0 / 0
```

```{r}
[1] NaN
```

```{r}
Inf - Inf
```

```{r}
[1] NaN
```

## Оценка результата

В результате работы была установлена библиотека swirl, а также были пройдены 5 подкурсов в рамках обучения "R Programming: The basics of programming in R"

## Вывод

Были изучены базовые команды и функции языка R - работа с переменными, векторами, файлами, циклами и NA.
