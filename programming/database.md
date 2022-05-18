# database

- vi ~/.bashrc
- PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
- PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w]\$ '
- . ~/.profile

## sqlite3

- dpkg -l | grep sql
- apt -y install sqlite3

- sqlite3
- .help

```sqlite3
  create table person(
    name char(20),
    age int);
```

- .table
- .schema
- .header on
- .mode column
- insert into person values('jsh', 40);
- select * from person;

- .quit

## mariadb

- dpkg -l | grep mariadb
- apt -y install mariadb-server
- apt install mysql-server

- systemctl status mariadb

## mysql

- dpkg -l | grep mysql

- service mysql start
- service --status-all | grep mysql
- ps -ef | grep mysql

- mysql
- ctrl + l (clear)

- select user();
- select now();

- show databases;
- use mysql;
- show tables;

- select user, password from user;
- update user set password=password('haby0921') where user='root';

- create user jsh identified by 'haby0921';
- delete from user where user='jsh';

- desc db;

```mysql
insert into db values ('localhost', 'jshDB', 'jsh',
'Y', 'Y', 'Y', 'Y',
'Y', 'Y', 'Y', 'Y',
'Y', 'Y', 'Y', 'Y',
'Y', 'Y', 'Y', 'Y',
'Y', 'Y', 'Y', 'Y');
```

- flush privileges;
- select Host, User, Select_priv, Insert_priv from user;

- exit;

- mysql -u jsh -p
- select user();
- show databases;
- create database jshDB;
- use jshDB;
- show tables;

```sqlite3
  create table person(
    name char(20),
    age int);
```

- desc person;
- insert into person values('jsh', 40);
- select * from person;
- update person set age=20 where name='jsh';
- delete from person where name='jsh';

- exit
