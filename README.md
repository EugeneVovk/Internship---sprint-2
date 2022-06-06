# Internship-Sprint-2

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
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/01.png)
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/02.png)

6.     Заполните созданные таблицы данными (данные смотрите ниже).
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/00.png)

7.     Вспомните или найдите информацию о том, какие бывают виды связей между таблицами.
		https://habr.com/ru/post/488054/
	Примените один вид связи для созданных таблиц.
	Один к одному
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/ER_Diagram.png)

8.     Вспомните или найдите информацию о том, что такое ER-диаграммы и зачем они нужны.
		https://habr.com/ru/post/440556/

9.     Заполните таблицы уникальными данными (важно: не меняйте ячейки с null) и сделайте скриншот получившейся таблицы. 
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/09.png)	

10.  Удалите строку с ID равным 1 из таблицы Users и сделайте скриншот получившегося результата. 
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/10.1.png)
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/10.2.png)

11.  Добавьте в таблицу Users строку с ID равным 1 и сделайте скриншот получившегося результата.
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/11.png)

ЭТАП 2. РАБОТА С ДАННЫМИ

-- 1. Выведите все поля из таблицы Users
	select * from Users;

-- 2. Выведите все поля из таблицы Clients
	select * from Clients;

-- 3. Посчитайте все записи в таблице Clients, где Name не равно null
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/03.png)

-- 4. Выведите все записи из таблицы Users, где Description не равно D3, а Type не равно null
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/04.png)

-- 5. Добавьте к 4-му запросу группировку по полю Type. Сделайте скриншот получившегося результата
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/05.png)

-- 6. Добавьте к 5-му запросу сортировку по возрастанию по полю Type
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/06.png)

-- 7. Выведите Name из двух таблиц, где Description не равно null
![Image alt](https://github.com/EugeneVovk/Internship-Sprint-2/raw/main/img/07.png)
