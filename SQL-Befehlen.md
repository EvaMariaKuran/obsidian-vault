[[show databases;]] 
[[create database datenbanknamen;]] 
[[use datenbanknamen;]]

[[show tables;]]
[[create table tablename (...);]]
[[describe tablename;]]

[[insert into tablename values (...);]] oder 
[[insert into tablename (.1.) values (.2.);]]

[[update tablename set ....;]]
[[update tablename set .....;]]

[[alter table tablename rename beispielname;]]
[[alter table tablename add column spaltenname timestamp;]]
[[alter table tablename drop column spaltenname;]]
[[alter table tablename change spaltenname spalte varchar(20) not null;]]
[[alter table tablename change spalte spalte varchar(40) not null;]]

[[delete from tablename where spaltenname=...; ]]
[[delete from tablename spaltenname;]] 

[[turncate tablename;]] 

[[drop database datenbanknamen;]]
[[drop tablename;]]

[[select * from tablename;]]
[[select * from tablename tablename2;]]
[[select * from tablename where ...;]]

[[select spaltenname from tablename;]]


[[\! clear]] 
[[\c]]
