## SQL — средний уровень

🏆 Правильных ответов: 11 из 12.

#### Q1. Получите список имен и фамилий сотрудников с зарплатой до 50 000 рублей из таблицы Employees.

|          |         |
| ----------- | ------- |
| employee_id | Integer |
| first_name  | String  |
| last_name   | String  |
| department  | String  |
| job_title   | String  |
| salary      | Integer |

- [ ] `CHOOSE first_name, last_name FROM Employees HAVING salary < 50000;`
- [x] `SELECT first_name, last_name FROM Employees WHERE salary < 50000;`
- [ ] `SELECT first_name, last_name WHERE salary < 50000 FROM Employees;`
- [ ] `SELECT first_name, last_name WHERE salary < 50000;`
- [ ] `FROM Employees SELECT first_name, last_name WHERE salary < 50000;`

#### Q2. Переименуйте столбец new_email в email в существующей таблице Clients.

- [x] `ALTER TABLE Clients RENAME COLUMN new_email TO email;`
- [ ] `ALTER TABLE Clients RENAME new_email TO email;`
- [ ] `UPDATE TABLE Clients RENAME new_email TO email;`
- [ ] `UPDATE TABLE Clients RENAME COLUMN new_email TO email;`
- [ ] `INTO TABLE Clients RENAME new_email TO email;`

#### Q3. Каким будет результат выполнения следующего кода для таблицы Cars, если car_id — первичный ключ с автоинкрементом? На изображении — элементы вывода таблицы.

`INSERT INTO Cars (distributor_id, car_model) VALUES (5, 'BMW X5 M50d');`


|  Cars     |         |
| -------------- | ------- |
| car_id         | Integer |
| distributor_id | Integer |
| car_model      | String  |
| number         | Integer |

Записи в таблице Cars

| car_id | distributor_id | car_model              | number |
| ------ | -------------- | ---------------------- | ------ |
| 1      | 1              | BMW X5 M50d           | 10     |
| 2      | 2              | Mercedez-Benz C-Class | 7      |
| 3      | 3              | Lexus LX               | 7      |

- [ ] Добавится новая запись `(Null, 5, 'BMW X5 M50d', Null)`
- [ ] Заменится последняя запись на новую `(3, 5, 'BMW X5 M50d', Null)`
- [ ] Заменится последняя запись на новую `(3, 5, 'BMW X5 M50d', 7)`
- [x] Добавится новая запись `(4, 5, 'BMW X5 M50d', Null)`
- [ ] Отобразится ошибка

#### Q4. Отсортируйте все покупки от последней к первой, а по каждому дню — от меньшей суммы продаж к большей в таблице Sales.

|          |         |
| ------------ | ------- |
| sale_id      | Integer |
| employee_id  | Integer |
| sale_title | String  |
| date         | Date    |
| sale_amount  | Double  |

- [x] `SELECT * FROM Sales ORDER BY date DESC, sale_amount ASC;`
- [ ] `SELECT * FROM Sales ORDER BY date, sale_amount;`
- [ ] `SELECT * FROM Sales SORT BY date DESC, sale_amount ASC;`
- [ ] `SELECT * FROM Sales ORDER BY date, sale_amount DESC, ASC;`
- [ ] `SELECT * FROM Sales ORDER BY sale_amount ASC, date DESC;`

#### Q5. Найдите модуль разницы между средней и максимальной заработной платой сотрудников в таблице Employees.

|          |         |
| ----------- | ------- |
| employee_id | Integer |
| first_name  | String  |
| last_name   | String  |
| department  | String  |
| job_title   | String  |
| salary      | Integer |

- [ ] `SELECT ABS(SUM(*)/COUNT(*) - MAX(salary)) FROM Employees;`
- [ ] `SELECT MEDIAN(salary) - MAX(salary) FROM Employees;`
- [ ] `SELECT AVG(salary) - MAX(salary) FROM Employees;`
- [x] `SELECT ABS(AVG(salary) - MAX(salary)) FROM Employees;`
- [ ] `SELECT ABS(MEDIAN(salary) - MAX(salary)) FROM Employees;`

#### Q6. Найдите численность населения городов, оканчивающихся на -burg, по регионам в таблице Cities.

|          |         |
| ------------ | ------- |
| city_id      | Integer |
| city_name    | String  |
| region_id | Integer |
| population   | Double  |
| rating       | Double  |

- [ ] `SELECT SUM(population) FROM Cities GROUP BY region_id HAVING city_name LIKE '%burg';`
- [x] `SELECT region_id, SUM(population) FROM Cities WHERE city_name LIKE '%burg' GROUP BY region_id;`
- [ ] `SELECT region_id, SUM ALL population FROM Cities WHERE city_name LIKE '%burg' GROUP BY region_id;`
- [ ] `SELECT region_id, SUM(population) FROM Cities GROUP BY region_id HAVING city_name LIKE '%burg';`
- [ ] `SELECT region_id, population FROM Cities WHERE city_name LIKE '%burg' GROUP BY region_id;`

#### Q7. Получите список сотрудников, содержащий названия их отделов, а также имена и фамилии сотрудников в столбце employees_list, из таблиц Employees и Departments, учитывая, что общий столбец между ними — dep_id.

|          |         |
| ------------- | ------- |
| emp_id        | Integer |
| dep_id        | Integer |
| first_name    | String  |
| second_name | String  |
| job_title     | String  |

|          |         |
|----------|---------|
| dep_id   | Integer |
| dep_name | String  |

- [ ] `SELECT dep_name, ADD(first_name, second_name) AS employees_list FROM Employees INNER JOIN Departments ON Employees.dep_id = Departments.dep_id;`
- [ ] `SELECT dep_name, (first_name + second_name) AS employees_list FROM Employees RIGHT JOIN Departments ON Employees.dep_id = Departments.dep_id;`
- [ ] `SELECT dep_name, JOIN(first_name, ' ', second_name) AS employees_list FROM Employees LEFT JOIN Departments ON Employees.dep_id = Departments.dep_id;`
- [ ] `SELECT dep_name, SUM(first_name, ' ', second_name) AS employees_list FROM Employees OUTER JOIN Departments ON Employees.dep_id = Departments.dep_id;`
- [x] `SELECT dep_name, CONCAT(first_name, ' ', second_name) AS employees_list FROM Employees INNER JOIN Departments ON Employees.dep_id = Departments.dep_id;`

#### Q8. Найдите имена сотрудников, зарплата которых больше средней зарплаты всех сотрудников в таблице Employees.

|          |         |
| ----------- | ------- |
| employee_id | Integer |
| first_name  | String  |
| last_name   | String  |
| department  | String  |
| job_title   | String  |
| salary      | Integer |

- [ ] `SELECT first_name, last_name FROM Employees WHERE AVG(salary) > salary;`
- [x] `SELECT first_name, last_name FROM Employees WHERE salary > (SELECT AVG(salary) FROM Employees);`
- [ ] `SELECT first_name, last_name FROM Employees WHERE salary > AVG(salary);`
- [ ] `SELECT first_name, last_name FROM Employees WHERE (SELECT SUM(salary) / COUNT(*) FROM employees) > salary;`
- [ ] `SELECT first_name, last_name FROM Employees GROUP BY first_name, last_name HAVING salary > AVG(salary);`

#### Q9. Вам нужно добавить столбец city в представление PeopleView с данными из двух таблиц Respondents и Info, содержащее возраст, телефоны и адреса респондентов. Какая ошибка допущена в запросе?

```
CREATE VIEW PeopleView OR REPLACE
AS SELECT Respondents.age, Respondents.city, Info.phone_number, Info.address
FROM Respondents, Info WHERE Respondents.respondent_id = Info.respondent_id;
```


|  Respondents  |         |
| -------------- | ------- |
| respondent_id  | Integer |
| city           | String  |
| age            | Integer |
| phone_number   | String  |
| know_languages | Array   |

|   Info  |         |
| ------------- | ------- |
| info_id       | Integer |
| respondent_id | Integer |
| phone_number  | String  |
| address       | String  |

- [ ] Не нужно указывать обе таблицы в строке с FROM
- [ ] Перед SELECT есть AS, который не нужен
- [x] Вместо CREATE VIEW PeopleView OR REPLACE нужно написать CREATE OR REPLACE VIEW PeopleView
- [ ] В запросе не нужно использовать VIEW
- [ ] Не нужно указывать, из каких таблиц взяты данные, можно написать age, phone_number, city, address

#### Q10. Индексацию какого столбца следует рассмотреть в первую очередь, если необходимо проиндексировать таблицу для повышения производительности запросов?

- [x] Столбец с большим количеством уникальных значений
- [ ] Столбец с большим количеством значений Null
- [ ] Столбец с двумя различными значениями (например, да/нет)
- [ ] Столбец, который часто обновляется
- [ ] Столбец, который используется в операторах SELECT без WHERE

#### Q11. Выберите ОШИБОЧНОЕ утверждение об обработке транзакций в языке SQL.

- [ ] Транзакции могут быть вложенными, то есть одна транзакция может содержать другую
- [ ] При исполнении транзакции можно выбрать, какие операции внутри нее должны быть выполнены, а какие — нет
- [ ] Операции отмены транзакции выполняются в порядке, обратном порядку их записи в файл журнала транзакций
- [x] Параллельное выполнение транзакций возможно, только если эти транзакции независимы и не влияют друг на друга
- [ ] Фиксация транзакции обеспечивает сохранение изменений в базе данных, сделанных при выполнении этой транзакции

#### Q12. Какой фактор следует учитывать в первую очередь для повышения производительности запроса, включающего несколько объединений:

```
SELECT * FROM table1
INNER JOIN table2 ON table2.id = table1.order_id
INNER JOIN table3 ON table3.id = table2.client_id;
```

- [ ] Соглашение об именах таблиц
- [ ] Наличие ограничения первичного ключа для присоединяемых столбцов
- [ ] Количество строк в результирующем наборе
- [x] Порядок соединения таблиц
- [ ] Типы данных соединяемых столбцов
