SQL> create table itstudent4(name varchar2(15),username varchar2(15)); Table created. 
SQL> create or replace trigger student4 before insert on student4 for each row 
2	declare 
3	name varchar2(20); 
4	begin 
5	select user into name from dual; 
6	:new.username:=name; 
7	end; 
8	/ 
Trigger created. 
Output: 
SQL> insert into student4 values('&name','&username'); 
Enter value for name: akbar Enter value for username: ranjani 
old 1: insert into student4 values('&name','&username') new 1: insert into student4 values('akbar','ranjani') 1 row created. 
SQL> / 
Enter value for name: suji Enter value for username: priya 
old 1: insert into student4 values('&name','&username') new 1: insert into student4 values('suji','priya') 1 row created. 
SQL> select * from itudent4; 
NAME USERNAME 
--------------- --------------- 
akbar SCOTT 
    suji SCOTT 
