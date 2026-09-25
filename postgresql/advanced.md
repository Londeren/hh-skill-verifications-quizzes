<!-- gg-cta:top:start -->
> [!TIP]
> **Ищете работу? [Проверьте, готовы ли вы работать на международном рынке →](https://t.me/just_solve_it_bot?start=u=2078385-s=4004822)**
>
> [Пройдите тест за 2 минуты и узнайте, что подтянуть первым →](https://t.me/just_solve_it_bot?start=u=2078385-s=4004822)
<!-- gg-cta:top:end -->

## PostgreSQL — продвинутый уровень

🏆 Правильных ответов: 14 из 15.

#### Q1. Существует структура базы данных. Какая команда на месте […] позволит создать новую запись в таблице role?

```
-- структура базы данных
create type permission as enum (
‘read',
‘write',
‘execute'
) ;
…
create table role(
…
permissions permission[],
…
) ;
-- запрос
Insert into table(…) values (…,[…],…);
```

- [x] array[‘read’]::permission[]

#### Q2. Какое утверждение относительно генерируемых колонок является ложью?

- [x] Генерируемые колонки могут ссылаться на другие генерируемые колонки

#### Q3. Имеется следующая структура, представленная на изображении. Было решено во все существующие записи в таблице role добавить пермиссию ‘read’ так, чтобы не было дубликатов. Как этого достичь?

```
Create type permission as enum (‘read’,’write’,’execute’,’transfer’,’download’);
Create table role(
…
Permissions permission[],
…
);
```

- [x] Update role set permissions = array_append(permissions,’read’) where array_position(permission, ‘read’) is null

#### Q4. Вы создаете временную таблицу temp_data, объединяя результаты двух запросов с несовместимыми типами данных (например, integer и text).

Требования:

- Автоматически принимать структуру первого запроса
- Сохранять дублирующиеся строки

Какой подход использовать?

```
Create temporary table temp_data as
<оператор> select id, data from source1,
<оператор> select id, into from source2;
```

- [x] Использовать UNION ALL, чтобы сохранить дубликаты и автоматически привести типы данных

#### Q5. У вас есть две связанные таблицы, где t2 использует значение из последовательности по умолчанию при обновлении ссылочной записи. Какие проблемы могут возникнуть при удалении записей из t1?

```
Create sequence seq start with 1 increment by 1;
Create table t1(
Id serial primary key
);
Create table t2(
Id integer default nextval(‘seq’) references t1(id) on delete set default
);
```

- [x] Удаление записи из t1 приведет к изменению ссылающихся записей в t2 на значение по умолчанию из последовательности, что может нарушать логику приложения

#### Q6. В таблице some_table содержится 1 миллион записей. На колонке id создан B-Tree индекс, а на колонке name — GIN-индекс для полнотекстового поиска. Какой запрос будет оптимально использовать индексы, если выборка данных составляет менее 0.1% от общего объёма?

```
Create table some_table(
Id serial,
Name varchar(30),
Description text
);
Create index some_table_id_index on some_table using btree(id);
Create index some_table_name_gin_index on some_table using gin(to_tsvector(‘english’,
name));
```

- [x] Select * from some_table where to_tsvector(‘english’, name) @@ to_tsquery('example');

#### Q7. Таблица logs содержит миллиарды записей и используется для анализа активности. Наиболее частый запрос к таблице выбирает записи по колонке user_id и фильтрует их по диапазону значений в колонке event_time. Какой индекс лучше всего подходит для ускорения выполнения запроса?

```
Create table logs (
Id serial primary key,
User_id integer not null,
Event_time timestamp not null,
Action text
);
-- Часто используемый запрос
Select * from logs
Where user_id = 12345 and event_time between ‘2024-01-01’ and ‘2024-01-01';
```

- [x] Create index logs_user_event_index on logs(user_id, event_time);

#### Q8. Существует таблица some_table:

| Class | Value |
|-------|-------|
| 1     | 10    |
| 1     | 20    |
| 1     | 100   |
| 2     | 200   |

Запускаются две транзакции — t1 и t2. Какой уровень изоляции транзакций НЕ позволит выполнить commit?

```
--t1
Select SUM(value) from mytab where class = 1;
Insert into some_table(class, value) values (2, 30);
Commit
--t2
Select SUM(value) from mytab where class = 2;
Insert into some_table(class, value) values (1, 300;
Commit;
```

- [x] Serializable

#### Q9. В PostgreSQL вы создаете индекс в транзакции над таблицей users. Во время выполнения этой транзакции другая транзакция пытается выполнять одну из следующих команд над той же таблицей. Какая команда выполнится без конфликтов?

```
-- Первая транзкация
Begin;
Create index idx_users_name on users(name);
--Вторая транзакция
<выбранная команда>
```

- [x] Select * from users;

#### Q10. Какие утверждения о следующем запросе правдивы?

```
Create materialized view some_view as select * from some_table order by id desc with
no data
```

- [x] Для представления some_view можно создать индекс

#### Q11. У вас есть рабочая база данных с высокой нагрузкой и ее копия. Вы хотите проанализировать производительность запроса, чтобы исключить влияние нагрузки на результаты анализа. Какую команду следует использовать для тестирования на копии базы данных.

- [x] explain (analyze, buffers)

#### Q12. В таблице orders содержится 1 миллион записей. На колонке customer_id есть индекс B-Tree. Вы выполняете следующий запрос с фильтрацией по customer_id и выбираете 90% строк. Какой тип сканирования таблицы будет использован планировщиком PostgreSQL?

```
Create table orders(
Order_id serial primary key,
Customer_id integer not null,
Order_date date,
Total_amount numeric
);
--Индекс
Create index idx_orders_customer_id on orders(customer_id);
--Запрос
Explain select * from orders where customer_id < 900000;
```

- [x] Seq scan

#### Q13. Существует таблица, представленная на изображении. В эту таблицу сохраняются данные, журналирующие некоторые действия. После очередного релиза частота вставки записей, где action=’login’, возросла в десять раз. Оперативно релиз починить не удается, но есть доступ к базе данных. Было решено временно не вставлять данные, где action=’login’, сохранив уже существующие записи.

```
Create table action_log(
Id serial
Action varchar,
Description text
);
```

- [x] Создать before insert trigger, запрещающий ‘login’

#### Q14. В PostgreSQL пользователь manuel должен получить полный доступ к таблице kinds. Следующая команда выполнена другим пользователем. Какой будет результат выполнения команды, если исполняющий пользователь не является суперпользователем и не является владельцем таблицы?

- [x] Команда завершится ошибкой, так как исполнитель команды не является владельцем таблицы

#### Q15. По мере продвижения бизнеса росло количество запросов к базе данных, а именно возросло в несколько раз количество запросов на запись при том же уровне запросов на чтение и повысить требования к отказоустойчивости. Какими методиками можно воспользоваться для поддержания работоспособности сервиса с учетом того, что запросов пол ключу большинство?

- [x] Репликация вместе с горизонтальным шардированием

<!-- gg-cta:bottom:start -->

---

### Что еще пригодится в поиске работы

- **[Проверьте, готовы ли вы работать на международном рынке →](https://t.me/just_solve_it_bot?start=u=2078385-s=4004822)** — тест на 2 минуты покажет, что подтянуть первым.
- **[Найдите работу в зарубежной компании, где команды часто говорят на русском →](https://t.me/just_solve_it_bot?start=u=2077530-s=3948364)** — таблица на 500+ компаний с русскоязычными корнями.
- **[Оформите профиль LinkedIn за 15 минут так, чтобы вас сами находили рекрутеры →](https://t.me/just_solve_it_bot?start=u=2077531-s=3847197)** — готовый промпт.

Все материалы бесплатные, из канала [«Серёга, разберись!» @just_solve_it](https://t.me/+IxvDIF9Yk51mNzcy). Канал — о том, как айтишнику выйти на международный рынок с оффером 5000+$
<!-- gg-cta:bottom:end -->
