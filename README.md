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
--![image](https://user-images.githubusercontent.com/45406197/181280157-5e3bc201-659a-48c5-92d7-b86fe0e0cf8c.png)

8 создайте новую роль readonly
--![image](https://user-images.githubusercontent.com/45406197/181280443-9d79f768-2c0f-4acc-9194-f6065c9ff4ef.png)

9 дайте новой роли право на подключение к базе данных testdb
--![image](https://user-images.githubusercontent.com/45406197/181312565-daf1aed7-f1fe-46fe-aa70-810a6524949f.png)

10 дайте новой роли право на использование схемы testnm
--![image](https://user-images.githubusercontent.com/45406197/181312734-07ed9ab3-27c5-48bd-800d-4d75ad84cea0.png)

11 дайте новой роли право на select для всех таблиц схемы testnm
--![image](https://user-images.githubusercontent.com/45406197/181312930-68f9501a-7e91-4396-b3d0-87c8b2d87cb2.png)

12 создайте пользователя testread с паролем test123
--![image](https://user-images.githubusercontent.com/45406197/181313062-8f21db2b-43a7-4973-89ac-f0ea73912bce.png)

13 дайте роль readonly пользователю testread
--![image](https://user-images.githubusercontent.com/45406197/181313530-63e287fa-0f31-4888-97ac-cafe4185bdb2.png)

14 зайдите под пользователем testread в базу данных testdb
--![image](https://user-images.githubusercontent.com/45406197/181340401-11df66c0-763b-421d-a861-e4bd0fca5d17.png)

15 сделайте select * from t1;
16 получилось? (могло если вы делали сами не по шпаргалке и не упустили один существенный момент про который позже)
--да, если обратиться к testnm.t1

--![image](https://user-images.githubusercontent.com/45406197/181340849-248ef7cd-c577-472e-97b0-7094a0a9b3c6.png)

17 напишите что именно произошло в тексте домашнего задания
18 у вас есть идеи почему? ведь права то дали?
19 посмотрите на список таблиц
20 подсказка в шпаргалке под пунктом 20
21 а почему так получилось с таблицей (если делали сами и без шпаргалки то может у вас все нормально)
22 вернитесь в базу данных testdb под пользователем postgres
--![image](https://user-images.githubusercontent.com/45406197/181341661-1d8938fd-0645-449d-8f92-f6d1dd121073.png)

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
--![image](https://user-images.githubusercontent.com/45406197/181343786-6c4b500b-4195-432a-bc4f-7e92b0142392.png)

32 получилось?
33 ура!
34 теперь попробуйте выполнить команду create table t2(c1 integer); insert into t2 values (2);
--![image](https://user-images.githubusercontent.com/45406197/181343975-60dc8c89-5055-44b4-8bfa-246dadc2c4f6.png)

35 а как так? нам же никто прав на создание таблиц и insert в них под ролью readonly?
36 есть идеи как убрать эти права? если нет - смотрите шпаргалку
37 если вы справились сами то расскажите что сделали и почему, если смотрели шпаргалку - объясните что сделали и почему выполнив указанные в ней команды

38 теперь попробуйте выполнить команду create table t3(c1 integer); insert into t2 values (2);
--![image](https://user-images.githubusercontent.com/45406197/181344638-6b6afa49-eec6-4c06-a331-49ec810c16ed.png)

39 расскажите что получилось и почему  
-- Команда REVOKE лишает одну или несколько ролей прав, назначенных ранее. 
Ключевое слово PUBLIC обозначает неявно определённую группу всех ролей.

