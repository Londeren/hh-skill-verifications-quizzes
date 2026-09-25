<!-- gg-cta:top:start -->
> [!TIP]
> **Ищете работу? [Проверьте, готовы ли вы работать на международном рынке →](https://t.me/just_solve_it_bot?start=u=2078385-s=4004822)**
>
> [Пройдите тест за 2 минуты и узнайте, что подтянуть первым →](https://t.me/just_solve_it_bot?start=u=2078385-s=4004822)
<!-- gg-cta:top:end -->

## Java — средний уровень

#### Содержание
* Строки в Java
* Принципы ООП
* Обработка ошибок

🏆 Правильных ответов: 12 из 12.

#### Q1. Приведенная ниже программа не компилируется, какая ошибка допущена?
```java
class Printer {
    public static void print(String message) {
        System.out.println(message);
    }
}
public class Example {
    private static void main (String name, int age) { // memod 1
        if (age >= 18) {
            String message = name + " is adult";
        } else {
            String message = name + "is not adult";
        }
        Printer printer = null;
        printer.print(message);
    }
    public static void main(String[] args) { // метод 2
    main ("Alex", 18);
    }
}
```

- [x] Использование переменной вне ее области видимости

#### Q2. Что выведет фрагмент кода?

```java
int day = 4;
switch (day) {
    case 1:
        System.out.print("One");
        break;
    case 2:

    case 4:
        System.out.print("Four");
        day = 1;
    case 5:
        System.out.print("Five");
}
```

- [x] FourFive

#### Q3. Что произойдет в данной программе?

```java
System.out.print("Hello");
while (1) {
    System.out.println(" World");
    break;
}
```

- [x] Программа не скомпилируется

#### Q4. В программе необходимо хранить температуру воды в градусах Цельсия в рамках теста, где она может колебаться от 0 до 100 градусов (только целые значения). Какой из перечисленных ниже типов данных вы бы выбрали для хранения температуры?

- [x] byte

#### Q5. Что такое стирание типов (type erasure) в контексте Generics?

- [x] Процесс, при котором компилятор удаляет информацию о параметрах generic-типа во время компиляции, заменяя их на ограничивающие типы или Object

#### Q6. Имеются два параметризованных списка. Какой тип будет у объектов этих списков после стирания типов?

```java
List‹? extends Number> list1;
List‹? super Integer> list2;
```

- [x] Для list1 типом будет Number, для list2 - Object

#### Q7. Что выведет программа?

```java
String str1 = "HelloWorld";
String temp = "World";

String str2 = "Hello" + "World";
String str3 = "Hello" + temp;
String str4 = new String("HelloWorld");

System.out.print("str1 == str2: " + (str1 == str2) + "; ");
System.out.print("str1 == str3: " + (str1 == str3) + "; ");
System.out.print("str1 == str4: " + (str1 == str4));
```

- [x] str1 == str2: true; str1 == str3: false; str1 == str4: false

#### Q8. Что выведет программа?

```java
public static void main(String[] args) {
    interface A {
        default void foo() {
            System.out.println("A");
        }
    }
    interface B {
        default void foo() {
            System.out.println("B");
        }
    }
    class C implements A, B {
        @Override
        public void foo() {
            System.out.println("Foo");
        }
    }
    A c = new C();
    c.foo();
}
```

- [x] Foo

#### Q9. Какое из следующих утверждений об интерфейсах в Java верно? (Java 8+)

- [x] Интерфейс может содержать статические методы с реализацией

#### Q10. В чем основное отличие между проверяемыми (checked) и НЕпроверяемыми (unchecked) исключениями в Java?

- [x] Проверяемые исключения обязательно должны быть объявлены в сигнатуре метода или обработаны, а непроверяемые нет

#### Q11. В чем преимущество использования ExecutorService для управления потоками по сравнению с ручным созданием и управлением фиксированным количеством потоков с помощью класса Thread?

- [x] Упрощает управление потоками за счет их повторного использования и предоставляет встроенные средства для планирования

#### Q12. Что произойдет с потоком, если он попытается войти в synchronized блок, который уже занят другим потоком?

- [x] Заблокируется до тех пор, пока другой поток не освободит монитор, после чего продолжит выполнение

<!-- gg-cta:bottom:start -->

---

### Что еще пригодится в поиске работы

- **[Проверьте, готовы ли вы работать на международном рынке →](https://t.me/just_solve_it_bot?start=u=2078385-s=4004822)** — тест на 2 минуты покажет, что подтянуть первым.
- **[Найдите работу в зарубежной компании, где команды часто говорят на русском →](https://t.me/just_solve_it_bot?start=u=2077530-s=3948364)** — таблица на 500+ компаний с русскоязычными корнями.
- **[Оформите профиль LinkedIn за 15 минут так, чтобы вас сами находили рекрутеры →](https://t.me/just_solve_it_bot?start=u=2077531-s=3847197)** — готовый промпт.

Все материалы бесплатные, из канала [«Серёга, разберись!» @just_solve_it](https://t.me/+IxvDIF9Yk51mNzcy). Канал — о том, как айтишнику выйти на международный рынок с оффером 5000+$
<!-- gg-cta:bottom:end -->
