上一节我们知道，通过 SQL，您可以从一个表复制信息到另一个表。
INSERT INTO SELECT 语句从一个表复制数据，然后把数据插入到一个已存在的表中。

SQL INSERT INTO SELECT 语法
我们可以从一个表中复制所有的列插入到另一个已存在的表中：

----------------------------------------------------
INSERT INTO table2
SELECT * FROM table1;
----------------------------------------------------

或者我们可以只复制希望的列插入到另一个已存在的表中：

----------------------------------------------------
INSERT INTO table2
(column_name(s))
SELECT column_name(s)
FROM table1;
----------------------------------------------------

复制 "apps" 中的数据插入到 "Websites" 中：

----------------------------------------------------
mysql> insert into websites(name,country)
    -> select app_name,country from apps;
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from websites;
+----+--------------+---------------------------+-------+---------+
| id | name         | url                       | alexa | country |
+----+--------------+---------------------------+-------+---------+
|  1 | Google       | https://www.google.cm/    |     1 | USA     |
|  2 | 淘宝         | https://www.taobao.com/   |    13 | CN      |
|  3 | 菜鸟教程     | http://www.runoob.com/    |  4689 | CN      |
|  4 | 微博         | http://weibo.com/         |    20 | CN      |
|  5 | Facebook     | https://www.facebook.com/ |     3 | USA     |
|  6 | QQ APP       |                           |     0 | CN      |
|  7 | 微博 APP     |                           |     0 | CN      |
|  8 | 淘宝 APP     |                           |     0 | CN      |
+----+--------------+---------------------------+-------+---------+
8 rows in set (0.00 sec)

mysql> 

----------------------------------------------------

只复 QQ 的 APP 到 "Websites" 中：
----------------------------------------------------
mysql> insert into websites (name,country) select app_name,country from apps where id=1;
Query OK, 1 row affected (0.01 sec)
Records: 1  Duplicates: 0  Warnings: 0

mysql> select * from websites;
+----+---------------+---------------------------+-------+---------+
| id | name          | url                       | alexa | country |
+----+---------------+---------------------------+-------+---------+
|  1 | Google        | https://www.google.cm/    |     1 | USA     |
|  2 | 淘宝          | https://www.taobao.com/   |    13 | CN      |
|  3 | 菜鸟教程      | http://www.runoob.com/    |  4689 | CN      |
|  4 | 微博          | http://weibo.com/         |    20 | CN      |
|  5 | Facebook      | https://www.facebook.com/ |     3 | USA     |
|  6 | stackoverflow | http://stackoverflow.com/ |     0 | IND     |
|  7 | QQ APP        |                           |     0 | CN      |
+----+---------------+---------------------------+-------+---------+
7 rows in set (0.00 sec)

mysql> 
----------------------------------------------------


补充
#######################################################################
select into from 和 insert into select 都是用来复制表
两者的主要区别为： select into from 要求目标表不存在，因为在插入时会自动创建；insert into select from 要求目标表存在。
1. 复制表结构及其数据：
create table table_name_new as select * from table_name_old
2. 只复制表结构：
create table table_name_new as select * from table_name_old where 1=2;
或者：
create table table_name_new like table_name_old
3. 只复制表数据：
如果两个表结构一样：
insert into table_name_new select * from table_name_old
如果两个表结构不一样：
insert into table_name_new(column1,column2...) select column1,column2... from table_name_old

#######################################################################
稍微整理一下 select into from 和 insert into select 的理解层面的区别
select into from ：将查询出来的数据整理到一张新表中保存，表结构与查询结构一致。
select *（查询出来的结果） into newtable（新的表名）from where （后续条件）
即，查询出来结果--->复制一张同结构的空表--->将数据拷贝进去。
insert into select ：为已经存在的表批量添加新数据。
insert into  (准备好的表) select *（或者取用自己想要的结构）from 表名 where 各种条件
即，指定一张想要插入数据的表格--->对数据进行加工筛选--->填入一张准备好的表格。
嗯，可能理解的比较粗浅，希望有知识经验的大佬及时订正。
