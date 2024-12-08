# Домашнее задание к занятию «Работа с данными (DDL/DML) - Козырев Ромна»


### Задание 1

1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp. 

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

1.4. Дайте все права для пользователя sys_temp. 

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос: 
```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*


### Решение 1

1.1 - 1.3
![image](https://github.com/user-attachments/assets/57181d09-922a-4c99-8fee-259ff36b7b3e)

1.4 - 1.5
![image](https://github.com/user-attachments/assets/fbcd918d-00d5-488e-8b0a-e27d6a04bc2e)
![image](https://github.com/user-attachments/assets/1e86c5f1-0b2a-465e-9d27-6aae540a3517)

1.6 - 1.8
![image](https://github.com/user-attachments/assets/0629a89a-a032-4b7d-8006-7cb74d9bf2ec)
![image](https://github.com/user-attachments/assets/dd4be9e0-66f7-4c07-af39-47c09768f761)
![image](https://github.com/user-attachments/assets/3a08b8c6-2c16-4dc0-85b0-42f1b4679121)


```sql
CREATE USER 'sys_test'@'localhost' IDENTIFIED BY 'password';
SELECT User,Host FROM mysql.user;
GRANT ALL PRIVILEGES ON db_name.* TO 'sys_test'@'localhost';
GRANT ALL PRIVILEGES ON *.* TO 'sys_test'@'localhost';
SHOW GRANTS FOR 'sys_test'@'localhost';
SELECT user ();
```

### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)
```
Название таблицы | Название первичного ключа
customer         | customer_id
```

### Решение 2
```
Название таблицы | Название первичного ключа
actor            | actor_id
address          | address_id
category         | category_id
city             | city_id
country          | country_id
customer         | customer_id
film             | film_id
film_actor       | actor_id, film_id
film_category    | film_id, category_id
film_text        | film_id
inventory        | inventory_id
language         | language_id
payment          | payment_id
rental           | rental_id
staff            | staff_id
store            | store_id
```
