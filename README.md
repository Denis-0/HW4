1 создайте новый кластер PostgresSQL 13 (на выбор - GCE, CloudSQL)
2 зайдите в созданный кластер под пользователем postgres
--![image](https://user-images.githubusercontent.com/45406197/181273907-318c66be-48ad-4112-b4ae-129a2df06c40.png)

3 создайте новую базу данных testdb
--![image](https://user-images.githubusercontent.com/45406197/181275059-2fda4114-7858-4e4b-a28d-2e4133c620c2.png)

4 зайдите в созданную базу данных под пользователем postgres
--![image](https://user-images.githubusercontent.com/45406197/181276164-d9243506-6e69-4099-bc55-8372e42a3216.png)

5 создайте новую схему testnm
--![image](https://user-images.githubusercontent.com/45406197/181277743-0c06f919-5f03-46ec-9cd6-c82c330b9577.png)

6 создайте новую таблицу t1 с одной колонкой c1 типа integer
--![image](https://user-images.githubusercontent.com/45406197/181279269-2148385f-99b0-41a7-834d-2ce74bf6e941.png)

7 вставьте строку со значением c1=1
8 создайте новую роль readonly
9 дайте новой роли право на подключение к базе данных testdb
10 дайте новой роли право на использование схемы testnm
11 дайте новой роли право на select для всех таблиц схемы testnm
12 создайте пользователя testread с паролем test123
13 дайте роль readonly пользователю testread
14 зайдите под пользователем testread в базу данных testdb
15 сделайте select * from t1;
16 получилось? (могло если вы делали сами не по шпаргалке и не упустили один существенный момент про который позже)
17 напишите что именно произошло в тексте домашнего задания
18 у вас есть идеи почему? ведь права то дали?
19 посмотрите на список таблиц
20 подсказка в шпаргалке под пунктом 20
21 а почему так получилось с таблицей (если делали сами и без шпаргалки то может у вас все нормально)
22 вернитесь в базу данных testdb под пользователем postgres
23 удалите таблицу t1
24 создайте ее заново но уже с явным указанием имени схемы testnm
25 вставьте строку со значением c1=1
26 зайдите под пользователем testread в базу данных testdb
27 сделайте select * from testnm.t1;
28 получилось?
29 есть идеи почему? если нет - смотрите шпаргалку
30 как сделать так чтобы такое больше не повторялось? если нет идей - смотрите шпаргалку
31 сделайте select * from testnm.t1;
32 получилось?
33 есть идеи почему? если нет - смотрите шпаргалку
31 сделайте select * from testnm.t1;
32 получилось?
33 ура!
34 теперь попробуйте выполнить команду create table t2(c1 integer); insert into t2 values (2);
35 а как так? нам же никто прав на создание таблиц и insert в них под ролью readonly?
36 есть идеи как убрать эти права? если нет - смотрите шпаргалку
37 если вы справились сами то расскажите что сделали и почему, если смотрели шпаргалку - объясните что сделали и почему выполнив указанные в ней команды
38 теперь попробуйте выполнить команду create table t3(c1 integer); insert into t2 values (2);
39 расскажите что получилось и почему  
