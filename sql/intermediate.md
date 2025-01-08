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

- [x] `SELECT first_name, last_name FROM Employees WHERE salary < 50000;`

#### Q2. Переименуйте столбец new_email в email в существующей таблице Clients.

- [x] `ALTER TABLE Clients RENAME COLUMN new_email TO email;`

#### Q3. Каким будет результат выполнения следующего кода для таблицы Cars, если car_id — первичный ключ с автоинкрементом? На изображении — элементы вывода таблицы.

```sql
INSERT INTO Cars (distributor_id, car_model) VALUES (5, 'BMW X5 M50d');
```


|  Cars          |         |
| -------------- | ------- |
| car_id         | Integer |
| distributor_id | Integer |
| car_model      | String  |
| number         | Integer |

Записи в таблице Cars

| car_id | distributor_id | car_model             | number |
| ------ | -------------- | --------------------- | ------ |
| 1      | 1              | BMW X5 M50d           | 10     |
| 2      | 2              | Mercedez-Benz C-Class | 7      |
| 3      | 3              | Lexus LX              | 7      |

- [x] Добавится новая запись `(4, 5, 'BMW X5 M50d', Null)`

#### Q4. Отсортируйте все покупки от последней к первой, а по каждому дню — от меньшей суммы продаж к большей в таблице Sales.

|              |         |
| ------------ | ------- |
| sale_id      | Integer |
| employee_id  | Integer |
| sale_title | String  |
| date         | Date    |
| sale_amount  | Double  |

- [x] `SELECT * FROM Sales ORDER BY date DESC, sale_amount ASC;`

#### Q5. Найдите модуль разницы между средней и максимальной заработной платой сотрудников в таблице Employees.

|             |         |
| ----------- | ------- |
| employee_id | Integer |
| first_name  | String  |
| last_name   | String  |
| department  | String  |
| job_title   | String  |
| salary      | Integer |

- [x] `SELECT ABS(AVG(salary) - MAX(salary)) FROM Employees;`

#### Q6. Найдите численность населения городов, оканчивающихся на -burg, по регионам в таблице Cities.

|              |         |
| ------------ | ------- |
| city_id      | Integer |
| city_name    | String  |
| region_id    | Integer |
| population   | Double  |
| rating       | Double  |

- [x] `SELECT region_id, SUM(population) FROM Cities WHERE city_name LIKE '%burg' GROUP BY region_id;`

#### Q7. Получите список сотрудников, содержащий названия их отделов, а также имена и фамилии сотрудников в столбце employees_list, из таблиц Employees и Departments, учитывая, что общий столбец между ними — dep_id.

|               |         |
| ------------- | ------- |
| emp_id        | Integer |
| dep_id        | Integer |
| first_name    | String  |
| second_name   | String  |
| job_title     | String  |

|          |         |
|----------|---------|
| dep_id   | Integer |
| dep_name | String  |

- [x] `SELECT dep_name, CONCAT(first_name, ' ', second_name) AS employees_list FROM Employees INNER JOIN Departments ON Employees.dep_id = Departments.dep_id;`

#### Q8. Найдите имена сотрудников, зарплата которых больше средней зарплаты всех сотрудников в таблице Employees.

|             |         |
| ----------- | ------- |
| employee_id | Integer |
| first_name  | String  |
| last_name   | String  |
| department  | String  |
| job_title   | String  |
| salary      | Integer |

- [x] `SELECT first_name, last_name FROM Employees WHERE salary > (SELECT AVG(salary) FROM Employees);`

#### Q9. Вам нужно добавить столбец city в представление PeopleView с данными из двух таблиц Respondents и Info, содержащее возраст, телефоны и адреса респондентов. Какая ошибка допущена в запросе?

```sql
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

- [x] Вместо CREATE VIEW PeopleView OR REPLACE нужно написать CREATE OR REPLACE VIEW PeopleView

#### Q10. Индексацию какого столбца следует рассмотреть в первую очередь, если необходимо проиндексировать таблицу для повышения производительности запросов?

- [x] Столбец с большим количеством уникальных значений

#### Q11. Выберите ОШИБОЧНОЕ утверждение об обработке транзакций в языке SQL.

- [x] При исполнении транзакции можно выбрать, какие операции внутри нее должны быть выполнены, а какие — нет

#### Q12. Какой фактор следует учитывать в первую очередь для повышения производительности запроса, включающего несколько объединений:

```sql
SELECT * FROM table1
INNER JOIN table2 ON table2.id = table1.order_id
INNER JOIN table3 ON table3.id = table2.client_id;
```

- [x] Порядок соединения таблиц
