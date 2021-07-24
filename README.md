# AddressBookMysqlShell

 MySQL  localhost:3306 ssl  payroll_service  SQL > show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mydb               |
| mysql              |
| payroll_service    |
| performance_schema |
| sakila             |
| sys                |
| test               |
| users              |
| world              |
+--------------------+
10 rows in set (0.2149 sec)

  UC-1  (create Database)
  
 MySQL  localhost:3306 ssl  payroll_service  SQL > create database Address_Book;
Query OK, 1 row affected (0.5215 sec)
 MySQL  localhost:3306 ssl  payroll_service  SQL > show databases;
+--------------------+
| Database           |
+--------------------+
| address_book       |
| information_schema |
| mydb               |
| mysql              |
| payroll_service    |
| performance_schema |
| sakila             |
| sys                |
| test               |
| users              |
| world              |
+--------------------+
11 rows in set (0.0264 sec)

  UC-2  (create table)

 MySQL  localhost:3306 ssl  address_book  SQL > create table addressBook
                                             -> (FirstName varchar(50) not null,
                                             -> LasrName varchar(50) not null,
                                             -> address varchar(200) not null,
                                             -> city varchar(50) not null,
                                             -> state varchar(50) not null,
                                             -> zip int not null,
                                             -> MobileNumber int not null,
                                             -> email varchar(100) not null);
Query OK, 0 rows affected (1.8182 sec)

 MySQL  localhost:3306 ssl  address_book  SQL > show tables;
+------------------------+
| Tables_in_address_book |
+------------------------+
| addressbook            |
+------------------------+

 MySQL  localhost:3306 ssl  address_book  SQL > describe addressbook;
+--------------+--------------+------+-----+---------+-------+
| Field        | Type         | Null | Key | Default | Extra |
+--------------+--------------+------+-----+---------+-------+
| FirstName    | varchar(50)  | NO   |     | NULL    |       |
| LasrName     | varchar(50)  | NO   |     | NULL    |       |
| address      | varchar(200) | NO   |     | NULL    |       |
| city         | varchar(50)  | NO   |     | NULL    |       |
| state        | varchar(50)  | NO   |     | NULL    |       |
| zip          | int          | NO   |     | NULL    |       |
| MobileNumber | int          | NO   |     | NULL    |       |
| email        | varchar(100) | NO   |     | NULL    |       |
+--------------+--------------+------+-----+---------+-------+
8 rows in set (0.0160 sec)

  UC-3  (Inaert)

MySQL  localhost:3306 ssl  address_book  SQL > insert into addressbook values ('Luffy','D','#1-234_Abcd road','Chittoor','Andhra',321,987654321,'abcd@gmail.com');
Query OK, 1 row affected (0.2013 sec)

 MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook tables;
 
+-----------+----------+------------------+----------+--------+-----+--------------+----------------+
| FirstName | LasrName | address          | city     | state  | zip | MobileNumber | email          |
+-----------+----------+------------------+----------+--------+-----+--------------+----------------+
| Luffy     | D        | #1-234_Abcd road | Chittoor | Andhra | 321 |    987654321 | abcd@gmail.com |
+-----------+----------+------------------+----------+--------+-----+--------------+----------------+
1 row in set (0.0339 sec)

 MySQL  localhost:3306 ssl  address_book  SQL > insert into addressbook values ('Garp','D','#2-433,Skyland road','Bangalore','Karnataka',321,987654321,'abcd@gmail.com');
Query OK, 1 row affected (0.1819 sec)
 MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook tables;
 
+-----------+----------+---------------------+-----------+-----------+-----+--------------+----------------+
| FirstName | LasrName | address             | city      | state     | zip | MobileNumber | email          |
+-----------+----------+---------------------+-----------+-----------+-----+--------------+----------------+
| Luffy     | D        | #1-234_Abcd road    | Chittoor  | Andhra    | 321 |    987654321 | abcd@gmail.com |
| Garp      | D        | #2-433,Skyland road | Bangalore | Karnataka | 321 |    987654321 | abcd@gmail.com |
+-----------+----------+---------------------+-----------+-----------+-----+--------------+----------------+
2 rows in set (0.0005 sec)

after inserting some data
 MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook tables;
 
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| FirstName | LasrName | address             | city      | state       | zip | MobileNumber | email          |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| Luffy     | D        | #1-234_Abcd road    | Chittoor  | Andhra      | 321 |    987654321 | abcd@gmail.com |
| Garp      | D        | #2-433,Skyland road | Bangalore | Karnataka   | 321 |    987654321 | abcd@gmail.com |
| Abcd      | E        | #2-433,Skyland road | roberls   | Delhi       | 123 |    987654321 | abcd@gmail.com |
| Sanji     | DS       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    753951468 | jajf@gmail.com |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+


  UC-4  (Edit)
MySQL  localhost:3306 ssl  address_book  SQL > update addressbook set MobileNumber=983216547 where FirstName='Sanji';                                        update addressbook set MobileNumber=983216547 where FirstName='Sanji';
Query OK, 1 row affected (0.1064 sec)

Rows matched: 1  Changed: 1  Warnings: 0
 MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook tables;
 
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| FirstName | LasrName | address             | city      | state       | zip | MobileNumber | email          |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| Luffy     | D        | #1-234_Abcd road    | Chittoor  | Andhra      | 321 |    987654321 | abcd@gmail.com |
| Garp      | D        | #2-433,Skyland road | Bangalore | Karnataka   | 321 |    987654321 | abcd@gmail.com |
| Abcd      | E        | #2-433,Skyland road | roberls   | Delhi       | 123 |    987654321 | abcd@gmail.com |
| Sanji     | DS       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    983216547 | jajf@gmail.com |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
4 rows in set (0.0275 sec)

  UC-5  (Delete)
MySQL  localhost:3306 ssl  address_book  SQL > delete from addressbook where FirstName='Abcd';
Query OK, 1 row affected (0.1877 sec)
 MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook tables;
 
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| FirstName | LasrName | address             | city      | state       | zip | MobileNumber | email          |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| Luffy     | D        | #1-234_Abcd road    | Chittoor  | Andhra      | 321 |    987654321 | abcd@gmail.com |
| Garp      | D        | #2-433,Skyland road | Bangalore | Karnataka   | 321 |    987654321 | abcd@gmail.com |
| Sanji     | DS       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    983216547 | jajf@gmail.com |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
3 rows in set (0.0005 sec)

  UC-6 (Ability to show Particular selected Data from DB)
  
   MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook where city='Bangalore';
   
+-----------+----------+---------------------+-----------+-----------+-----+--------------+----------------+
| FirstName | LasrName | address             | city      | state     | zip | MobileNumber | email          |
+-----------+----------+---------------------+-----------+-----------+-----+--------------+----------------+
| Garp      | D        | #2-433,Skyland road | Bangalore | Karnataka | 321 |    987654321 | abcd@gmail.com |
+-----------+----------+---------------------+-----------+-----------+-----+--------------+----------------+
1 row in set (0.0008 sec)

 MySQL  localhost:3306 ssl  address_book  SQL > insert into addressbook values ('Nami','SJ','#4543-3, lsdfj road','aqualand','UnderGround',654,753951468,'jajf@gmail.com');
Query OK, 1 row affected (0.1754 sec)
 MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook tables;
 
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| FirstName | LasrName | address             | city      | state       | zip | MobileNumber | email          |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| Luffy     | D        | #1-234_Abcd road    | Chittoor  | Andhra      | 321 |    987654321 | abcd@gmail.com |
| Garp      | D        | #2-433,Skyland road | Bangalore | Karnataka   | 321 |    987654321 | abcd@gmail.com |
| Sanji     | DS       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    983216547 | jajf@gmail.com |
| Nami      | SJ       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    753951468 | jajf@gmail.com |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
4 rows in set (0.0444 sec)

 MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook where state='UnderGround';
 
+-----------+----------+---------------------+----------+-------------+-----+--------------+----------------+
| FirstName | LasrName | address             | city     | state       | zip | MobileNumber | email          |
+-----------+----------+---------------------+----------+-------------+-----+--------------+----------------+
| Sanji     | DS       | #4543-3, lsdfj road | aqualand | UnderGround | 654 |    983216547 | jajf@gmail.com |
| Nami      | SJ       | #4543-3, lsdfj road | aqualand | UnderGround | 654 |    753951468 | jajf@gmail.com |
+-----------+----------+---------------------+----------+-------------+-----+--------------+----------------+
2 rows in set (0.0005 sec)

 
  UC-7 (ability to count States and Cities)
  
MySQL  localhost:3306 ssl  address_book  SQL > select count(city & state) from addressbook;
+---------------------+
| count(city & state) |
+---------------------+
|                   4 |
+---------------------+


  UC-8 (ability to keep Ordered)  
MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook order by FirstName asc;
 
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| FirstName | LasrName | address             | city      | state       | zip | MobileNumber | email          |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
| Garp      | D        | #2-433,Skyland road | Bangalore | Karnataka   | 321 |    987654321 | abcd@gmail.com |
| Luffy     | D        | #1-234_Abcd road    | Chittoor  | Andhra      | 321 |    987654321 | abcd@gmail.com |
| Nami      | SJ       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    753951468 | jajf@gmail.com |
| Sanji     | DS       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    983216547 | jajf@gmail.com |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+
4 rows in set (0.0308 sec)


  UC-9 (ability to find with particular data info)
  
MySQL  localhost:3306 ssl  address_book  SQL > select FirstName,city from addressbook order by FirstName asc;
+-----------+-----------+
| FirstName | city      |
+-----------+-----------+
| Garp      | Bangalore |
| Luffy     | Chittoor  |
| Nami      | aqualand  |
| Sanji     | aqualand  |
+-----------+-----------+
4 rows in set (0.0006 sec)


  UC-10 (count of Contact Persons)
  
 MySQL  localhost:3306 ssl  address_book  SQL > select count(mobilenumber) from addressbook;
+---------------------+
| count(mobilenumber) |
+---------------------+
|                   4 |
+---------------------+
1 row in set (0.0007 sec)

MySQL  localhost:3306 ssl  address_book  SQL > select mobilenumber from addressbook;
+--------------+
| mobilenumber |
+--------------+
|    987654321 |
|    987654321 |
|    983216547 |
|    753951468 |
+--------------+ 
  
  
  UC-11 (Adding type)
  
MySQL  localhost:3306 ssl  address_book  SQL > alter table addressbook add type varchar(50);
Query OK, 0 rows affected (2.2771 sec)

Records: 0  Duplicates: 0  Warnings: 0
MySQL  localhost:3306 ssl  address_book  SQL > update addressbook set type='ME' where firstname = 'luffy';
Query OK, 1 row affected (0.1642 sec)

Rows matched: 1  Changed: 1  Warnings: 0
MySQL  localhost:3306 ssl  address_book  SQL > update addressbook set type='Friend' where firstname = 'Sanji';
Query OK, 1 row affected (0.1126 sec)

Rows matched: 1  Changed: 1  Warnings: 0
MySQL  localhost:3306 ssl  address_book  SQL > update addressbook set type='Family' where firstname = 'Nami';
Query OK, 1 row affected (0.1118 sec)

Rows matched: 1  Changed: 1  Warnings: 0
MySQL  localhost:3306 ssl  address_book  SQL > select *from addressbook tables;

+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+--------+
| FirstName | LasrName | address             | city      | state       | zip | MobileNumber | email          | type   |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+--------+
| Luffy     | D        | #1-234_Abcd road    | Chittoor  | Andhra      | 321 |    987654321 | abcd@gmail.com | ME     |
| Garp      | D        | #2-433,Skyland road | Bangalore | Karnataka   | 321 |    987654321 | abcd@gmail.com | NULL   |
| Sanji     | DS       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    983216547 | jajf@gmail.com | Friend |
| Nami      | SJ       | #4543-3, lsdfj road | aqualand  | UnderGround | 654 |    753951468 | jajf@gmail.com | Family |
+-----------+----------+---------------------+-----------+-------------+-----+--------------+----------------+--------+
4 rows in set (0.0005 sec)
  
 
