## Научно-исследовательская работа на тему «Работа с данными SQLite из программ на языке Python» 
Здесь представлена третья часть работы, которая выполнялась в виде индивидуального задания.

---
## Исходные данные
Исходные данные для выполнения индивидуальных заданий – БД VUZ.sqlite, содержащая 2 таблицы:   
* Таблица vuzkart, cодержащая сведения о вузах России

| Ключ | Имя столбца | Тип данных | Описание                                                                                                                             |
| ---- | ----------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| 🔑    | codvuz      | char(6)    | Код   вуза                                                                                                                           |
|      | z1          | char(200)  | Полное   наименование вуза                                                                                                           |
|      | z1full      | char(250)  | Полное   юридическое наименование вуза                                                                                               |
|      | z2          | char(12)   | Сокращённое   наименование                                                                                                           |
|      | z2ustav     | char(100)  | Сокращённое   наименование по   уставу                                                                                               |
|      | foundyear   | integer(4) | Год   основания вуза                                                                                                                 |
|      | z8          | char(110)  | Юридический   адрес вуза                                                                                                             |
|      | z9          | char(40)   | Справочный   телефон вуза                                                                                                            |
|      | z12         | char(20)   | Номер   факса вуза                                                                                                                   |
|      | e_mail      | char(30)   | Адрес   электронной почты                                                                                                            |
|      | www         | char(30)   | Адрес   официального сайта вуза                                                                                                      |
|      | z15         | char(40)   | Ректор   вуза                                                                                                                        |
|      | region      | char(17)   | Федеральный округ                                                                                                                    |
|      | city        | char(20)   | Город                                                                                                                                |
|      | status      | char(15)   | Статус вуза                                                                                                                          |
|      | oblname     | char(40)   | Субъект   федерации                                                                                                                  |
|      | gr_ved      | char(3)    | Категория   вуза - принадлежность к ведущим вузам (ФУ – федеральный университет, НИУ –   национальный исследовательский университет) |
|      | prof        | char(2)    | Профиль   вуза: ИТ – инженерно-технический, КЛ – классический университет, ГП –   гуманитарно-педагогический, МП - многопрофильный   |

* Таблица vuzstat, содержащая статистические данные по вузам России

| Ключ | Имя столбца | Тип данных | Описание                                                    |
| ---- | ----------- | ---------- | ----------------------------------------------------------- |
| 🔑    | codvuz      | char(6)    | Код   вуза                                                  |
|      | PPS         | integer(4) | Численность   профессорско-преподавательского состава (ППС) |
|      | PR          | integer(4) | ППС   профессора                                            |
|      | DC          | integer(4) | ППС   доценты                                               |
|      | DN          | integer(4) | ППС   доктора наук                                          |
|      | KN          | integer(4) | ППС   кандидаты наук                                        |
|      | ZOB         | integer(4) | Количество   зданий-общежитий                               |
|      | STUD        | integer(4) | Количество   студентов, всего                               |
|      | BAC         | integer(4) | Обучается   по программам бакалавриата                      |
|      | SPEC        | integer(4) | Обучается   по программам подготовки специалистов           |
|      | MAG         | integer(4) | Обучается   по программам магистратуры                      |
|      | ST_OCH      | integer(4) | Студентов   по очной форме обучения                         |
|      | ST_OCH_Z    | integer(4) | Студентов по очно-заочной   форме обучения                  |
|      | ST_Z        | integer(4) | Студентов по заочной   форме обучения                       |
|      | ASP         | integer(4) | Аспирантов всего                                            |
|      | ASP_OCH     | integer(4) | Аспирантов по очной   форме обучения                        |


### Задание
---
1. Обеспечить выбор из списка статуса вуза, интересующего пользователя. Составить и отобразить на экране перечень полных наименований вузов, имеющих выбранный статус.  
2. Рассчитать и представить в виде таблицы распределение процента преподавателей, имеющих ученые степени, по профилям. Таблица должна иметь столбцы: порядковый номер, профиль, количество преподавателей, количество преподавателей с учеными степенями в вузах данного профиля, процентное отношение преподавателей со степенями к общему числу преподавателей. В шапке таблицы указываются названия столбцов. Нижняя строка таблицы – итоговая: с суммарными значениями количества преподавателей и количества «остепененных» преподавателей, а также общее процентное отношение этих значений.

### Пример работы программы после запуска:
---
```
Укажите имя файла SQLite: VUZ.sqlite

        Выберите действие(Введите цифру):
        1 - Отображение текущего содержимого обеих БД на экране в виде таблицы
        2 - Выбрать статус из списка статусов вуза и вывести все вузы с выбранным статусом 
        6 - Завершение работы с программой 

2

Введите статус из данного списка: {'Институт',,'Университет',,'Академия',}
УНИ
Такого статуса нет, введите еще раз
Введите статус из данного списка: {'Институт',,'Университет',,'Академия',}
Университет
Таблица:  vuzkart  из БД  VUZ.sqlite

```
| vuz_name                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------- |
| Алтайский государственный университет                                                                                            |
| Северный (Арктический) федеральный университет имени М.В. Ломоносова                                                             |
| Балтийский государственный технический университет "ВОЕНМЕХ" им. Д.Ф. Устинова                                                   |
| Амурский государственный университет                                                                                             |
| Брянский государственный технический университет                                                                                 |
| Владимирский государственный университет имени Александра Григорьевича и Николая Григорьевича Столетовых                         |
| Воронежский государственный архитектурно-строительный университет                                                                |
| Российский государственный университет нефти и газа имени И.М. Губкина                                                           |
| Государственный университет управления                                                                                           |
| Дагестанский государственный университет                                                                                         |
| Дагестанский государственный технический университет                                                                             |
| Дальневосточный федеральный университет                                                                                          |
| Ивановский государственный университет                                                                                           |
| Ивановский государственный химико-технологический университет                                                                    |
| Иркутский государственный технический университет                                                                                |
| Казанский национальный исследовательский технический университет им. А.Н. Туполева - КАИ                                         |
| Казанский национальный исследовательский технологический университет                                                             |
| Казанский (Приволжский) федеральный университет                                                                                  |
| Балтийский федеральный университет имени Иммануила Канта                                                                         |
| Калмыцкий государственный университет                                                                                            |
| Вятский государственный университет                                                                                              |

~~~
Укажите имя файла SQLite: VUZ.sqlite

        Выберите действие(Введите цифру):
        1 - Отображение текущего содержимого обеих БД на экране в виде таблицы
        2 - Выбрать статус из списка статусов вуза и вывести все вузы с выбранным статусом
        3 - Распределение процента преподавателей, имеющих ученые степени, по профилям 
        6 - Завершение работы с программой 
3

[N, Профиль, Кол-во преподователей, Кол-во преподователей с учеными степенями, Процентное отношение преподавателей со степенями к общему числу преподавателей]
[1, 'ИТ     ', 38479, 25428, 66.083]
[2, 'КЛ     ', 32657, 21592, 66.118]
[3, 'МП     ', 17950, 10852, 60.457]
[4, 'ГП     ', 13713, 9115, 66.47]
[ALL, ALL    , 102799 , 66987 , 65.163 ]

        Выберите действие(Введите цифру):
        1 - Отображение текущего содержимого обеих БД на экране в виде таблицы
        2 - Выбрать статус из списка статусов вуза и вывести все вузы с выбранным статусом
        3 - Распределение процента преподавателей, имеющих ученые степени, по профилям 
        6 - Завершение работы с программой 
6
~~~