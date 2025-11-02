# Lab3


## Цель работы

1.  Развить практические навыки использования языка программирования R
    для обработки данных
2.  Закрепить знания базовых типов данных языка R
3.  Развить практические навыки использования функций обработки данных
    пакета dplyr – функции select(), filter(), mutate(), arrange(),
    group_by()

## Исходные данные

1.  Windows 11
2.  Rstudio
3.  Github

## План

1.  Установить и загрузить библиотеку dplyr.
2.  Проанализировать набор данных starwars и получить ответы на вопросы:
3.  Оформить отчет в соответствии с шаблоном

## Содержание работы

### Шаг 1

Установка библиотеки dplyr

``` r
install.packages("dplyr")
```

Загрузка библиотеки dplyr

``` r
library("dplyr")
```

    Warning: пакет 'dplyr' был собран под R версии 4.4.2


    Присоединяю пакет: 'dplyr'

    Следующие объекты скрыты от 'package:stats':

        filter, lag

    Следующие объекты скрыты от 'package:base':

        intersect, setdiff, setequal, union

### Шаг 2

Анализ набора данных starwars

#### 1. Сколько строк в датафрейме?

``` r
starwars %>% nrow()
```

    [1] 87

#### 2. Сколько столбцов в датафрейме?

``` r
starwars %>% ncol()
```

    [1] 14

#### 3. Как просмотреть примерный вид датафрейма?

``` r
starwars %>% glimpse()
```

    Rows: 87
    Columns: 14
    $ name       <chr> "Luke Skywalker", "C-3PO", "R2-D2", "Darth Vader", "Leia Or…
    $ height     <int> 172, 167, 96, 202, 150, 178, 165, 97, 183, 182, 188, 180, 2…
    $ mass       <dbl> 77.0, 75.0, 32.0, 136.0, 49.0, 120.0, 75.0, 32.0, 84.0, 77.…
    $ hair_color <chr> "blond", NA, NA, "none", "brown", "brown, grey", "brown", N…
    $ skin_color <chr> "fair", "gold", "white, blue", "white", "light", "light", "…
    $ eye_color  <chr> "blue", "yellow", "red", "yellow", "brown", "blue", "blue",…
    $ birth_year <dbl> 19.0, 112.0, 33.0, 41.9, 19.0, 52.0, 47.0, NA, 24.0, 57.0, …
    $ sex        <chr> "male", "none", "none", "male", "female", "male", "female",…
    $ gender     <chr> "masculine", "masculine", "masculine", "masculine", "femini…
    $ homeworld  <chr> "Tatooine", "Tatooine", "Naboo", "Tatooine", "Alderaan", "T…
    $ species    <chr> "Human", "Droid", "Droid", "Human", "Human", "Human", "Huma…
    $ films      <list> <"A New Hope", "The Empire Strikes Back", "Return of the J…
    $ vehicles   <list> <"Snowspeeder", "Imperial Speeder Bike">, <>, <>, <>, "Imp…
    $ starships  <list> <"X-wing", "Imperial shuttle">, <>, <>, "TIE Advanced x1",…

#### 4. Сколько уникальных рас персонажей (species) представлено в данных?

``` r
starwars %>%
  select(species) %>%
  filter(!is.na(species)) %>%
  n_distinct()
```

    [1] 37

#### 5. Найти самого высокого персонажа.

``` r
starwars %>% arrange(desc(height)) %>% slice(1:1) %>% select(name)
```

    # A tibble: 1 × 1
      name       
      <chr>      
    1 Yarael Poof

#### 6. Найти всех персонажей ниже 170

``` r
starwars %>% 
  filter(height < 170) %>%
  select(name)
```

    # A tibble: 22 × 1
       name                 
       <chr>                
     1 C-3PO                
     2 R2-D2                
     3 Leia Organa          
     4 Beru Whitesun Lars   
     5 R5-D4                
     6 Yoda                 
     7 Mon Mothma           
     8 Wicket Systri Warrick
     9 Nien Nunb            
    10 Watto                
    # ℹ 12 more rows

#### 7. Подсчитать ИМТ (индекс массы тела) для всех персонажей.

``` r
starwars %>%
  mutate("IMB" = mass / height^2) %>%
  select(name, IMB)
```

    # A tibble: 87 × 2
       name                   IMB
       <chr>                <dbl>
     1 Luke Skywalker     0.00260
     2 C-3PO              0.00269
     3 R2-D2              0.00347
     4 Darth Vader        0.00333
     5 Leia Organa        0.00218
     6 Owen Lars          0.00379
     7 Beru Whitesun Lars 0.00275
     8 R5-D4              0.00340
     9 Biggs Darklighter  0.00251
    10 Obi-Wan Kenobi     0.00232
    # ℹ 77 more rows

#### 8. Найти 10 самых “вытянутых” персонажей. “Вытянутость” оценить по отношению массы (mass) к росту (height) персонажей.

``` r
starwars %>%
  mutate("long" = mass / height) %>%
  arrange(desc(long)) %>%
  slice_head(n=10) %>%
  select(name)
```

    # A tibble: 10 × 1
       name                 
       <chr>                
     1 Jabba Desilijic Tiure
     2 Grievous             
     3 IG-88                
     4 Owen Lars            
     5 Darth Vader          
     6 Jek Tono Porkins     
     7 Bossk                
     8 Tarfful              
     9 Dexter Jettster      
    10 Chewbacca            

#### 9. Найти средний возраст персонажей каждой расы вселенной Звездных войн.

``` r
starwars %>%
  group_by(species) %>%
  summarize(avg = mean(birth_year)) %>%
  filter(!is.na(avg)) %>%
  filter(!is.na(species))
```

    # A tibble: 9 × 2
      species          avg
      <chr>          <dbl>
    1 Cerean            92
    2 Ewok               8
    3 Hutt             600
    4 Kel Dor           22
    5 Mirialan          49
    6 Mon Calamari      41
    7 Rodian            44
    8 Trandoshan        53
    9 Yoda's species   896

#### 10. Найти самый распространенный цвет глаз персонажей вселенной Звездных войн.

``` r
starwars %>% 
  filter(!is.na(eye_color)) %>%  
  group_by(eye_color) %>% 
  summarise('Колличество'= n()) %>% 
  arrange(desc(Колличество)) %>% 
  select(eye_color, Колличество) %>% 
  slice(1)
```

    # A tibble: 1 × 2
      eye_color Колличество
      <chr>           <int>
    1 brown              21

#### 11. Подсчитать среднюю длину имени в каждой расе вселенной Звездных войн.

``` r
starwars %>% 
  mutate(len=nchar(name)) %>% 
  group_by(species) %>% 
  summarise('mean' = mean(len)) %>% 
  select(species,mean) %>%
  filter(!is.na(species))
```

    # A tibble: 37 × 2
       species    mean
       <chr>     <dbl>
     1 Aleena    12   
     2 Besalisk  15   
     3 Cerean    12   
     4 Chagrian  10   
     5 Clawdite  10   
     6 Droid      4.83
     7 Dug        7   
     8 Ewok      21   
     9 Geonosian 17   
    10 Gungan    11.7 
    # ℹ 27 more rows

## Оценка результатов

Задача выполнена при помощи RStudio, удалось познакомится с функционалом
и особенностями языка программирования R.

## Вывод

В данной работе успешно удалось познакомиться с языком R и выполнить
учебные задания по swirl.
