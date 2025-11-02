# Lab4

belosludtzev.vanya@yandex.ru

## Цель работы

1.  Изучить возможности технологии Yandex Query для анализа
    структурированных наборов данных
2.  Получить навыки построения аналитического пайплайна для анализа
    данных с помощью сервисов Yandex Cloud
3.  Закрепить практические навыки использования SQL для анализа данных
    сетевой активности в сегментированной корпоративной сети

## Исходные данные

1.  Windows 11
2.  Rstudio
3.  Github
4.  Yandex Cloud
5.  Yandex Query

## План выполнения работы

1.  Проверить доступность данных в Yandex Object Storage
2.  Подключить бакет как источник данных для Yandex Query
3.  Выполнить аналитические задания

## Содержание Работы

## Шаг 1. Проверить доступность данных в Yandex Object Storage

![](https://github.com/KartaviiBro/SecurityThreats/blob/main/Lab4/img/1.png)

## Шаг 2. Подключить бакет как источник данных для Yandex Query

1.  Создать соединение для бакета в S3 хранилище

![](https://github.com/KartaviiBro/SecurityThreats/blob/main/Lab4/img/2.png)

1.  Настройка привязки данных

![](https://github.com/KartaviiBro/SecurityThreats/blob/main/Lab4/img/3.png)

1.  Проверка корректности данных с помошью запроса

![](https://github.com/KartaviiBro/SecurityThreats/blob/main/Lab4/img/4.png)

## Шаг 3. Выполнить аналитические задания

1.  Известно, что IP адреса внутренней сети начинаются с октетов,
    принадлежащих интервалу \[12-14\]. Определите количество хостов
    внутренней сети, представленных в датасете.

![](https://github.com/KartaviiBro/SecurityThreats/blob/main/Lab4/img/5.png)

1.  Определите суммарный объем исходящего трафика

![](https://github.com/KartaviiBro/SecurityThreats/blob/main/Lab4/img/6.png)

1.  Определите суммарный объем входящего трафика

![](https://github.com/KartaviiBro/SecurityThreats/blob/main/Lab4/img/7.png)

## Оценка результата

В результате практической работы было созданое соединение для работы с
датасетом и выполнены аналитические задания

## Вывод

В результате выполнения практической работы были освоены инструменты
работы с Yandex Query

``` r
print('Работа выполнена')
```

    [1] "Работа выполнена"
