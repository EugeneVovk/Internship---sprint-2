# Internship---sprint-2

Тестирование баз данных

Вы наверняка знаете, что при авторизации в личном кабинете система обращается в базу данных и сверяет, существует ли пользователь с указанными авторизационными данными. После тестирования интерфейса вам предстоит погрузиться в тестирование баз данных. Тестировщик должен не только уметь писать простые запросы в БД, но и создавать тестовые базы данных в условиях, когда реальной базы еще не существует. Этим вы и займетесь на этой неделе.

Объект тестирования второй недели: Локальная БД

ЭТАП 1. СОЗДАНИЕ ДАННЫХ

Сперва вам необходимо заняться созданием данных.

1.     Скачайте и разверните PostgreSQL.

2.     Создайте БД.

3.     Установите Dbeaver.

4.     Создайте подключение к БД.

5.     Создайте две таблицы.
		- create table Users (ID int, Name text, Type text, Date text, Description text);
		- create table Clients (ID int, Name text, Country text, City text, Description text);

6.     Заполните созданные таблицы данными (данные смотрите ниже).
		- insert into Users (ID, Name, Type, Date, Description)
		  values (0, 'N1', 'T1', null, 'D1');
		
		- insert into Users (ID, Name, Type, Date, Description)
		  values (1, 'N2', 'T2', 'D2', 'D2');
		
		- insert into Users (ID, Name, Type, Date, Description)
		  values (2, 'N3', null, 'D3', 'D3');
		
		- insert into Clients (ID, Name, Country, City, Description)
		  values (0, 'N1', 'C1', 'C1', 'D1');
		
		- insert into Clients (ID, Name, Country, City, Description)
		  values (1, 'N2', 'C2', null, 'D2');
		
		- insert into Clients (ID, Name, Country, City, Description)
		  values (2, 'N3', 'C3', 'C3', null);

7.     Вспомните или найдите информацию о том, какие бывают виды связей между таблицами. Примените один вид связи для созданных таблиц.
		https://habr.com/ru/post/488054/

8.     Вспомните или найдите информацию о том, что такое ER-диаграммы и зачем они нужны.
		https://habr.com/ru/post/440556/

9.     Заполните таблицы уникальными данными (важно: не меняйте ячейки с null) и сделайте скриншот получившейся таблицы. 
		- insert into Users (ID, Name, Type, Date, Description)
		  values (3, 'John', 'amin', null, 'check');
		
		- insert into Users (ID, Name, Type, Date, Description)
		  values (4, 'Ann', 'dev', '01.01.2022', 'create');
		
		- insert into Users (ID, Name, Type, Date, Description)
		  values (5, 'Sasha', null, '10.03.2022', 'test');
		
		- insert into Clients (ID, Name, Country, City, Description)
		  values (3, 'Kate', 'USA', 'Eugene', 'cold');
		
		- insert into Clients (ID, Name, Country, City, Description)
		  values (4, 'Bob', 'Germany', null, 'warm');
		
		- insert into Clients (ID, Name, Country, City, Description)
		  values (5, 'Lucy', 'Japan', 'Date', null);		

10.  Удалите строку с ID равным 1 из таблицы Users и сделайте скриншот получившегося результата. 

11.  Добавьте в таблицу Users строку с ID равным 1 и сделайте скриншот получившегося результата.

ЭТАП 2. РАБОТА С ДАННЫМИ

-- 1. Выведите все поля из таблицы Users
	select * from Users;

-- 2. Выведите все поля из таблицы Clients
	select * from Clients;

-- 3. Посчитайте все записи в таблице Clients, где Name не равно null
	select count(*) from Clients where not Name='null';

-- 4. Выведите все записи из таблицы Users, где Description не равно D3, а Type не равно null
	select * from Users where not Description='D3' or Type='null';

-- 5. Добавьте к 4-му запросу группировку по полю Type. Сделайте скриншот получившегося результата
	select Type from Users 
	where not Description='D3' or Type='null'
	group by Type;

-- 6. Добавьте к 5-му запросу сортировку по возрастанию по полю Type
	select Type from Users 
	where not Description='D3' or Type='null'
	group by Type
	order by Type asc;

-- 7. Выведите Name из двух таблиц, где Description не равно null
	select Users.Name as Users, Clients.Name as Clients 
	from Users
	left join Clients
	on Users.Description=Clients.Description
	where Users.Description is not null or Clients.Description is not null;
