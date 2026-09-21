## Java — продвинутый уровень

<!-- gg-cta:top:start -->
> [!TIP]
> **Ищете работу? Два бесплатных материала в Telegram-боте:**
>
> - [500+ зарубежных IT-компаний с русскоязычными корнями](https://t.me/just_solve_it_bot?start=u=2077530-s=3948364) — найдите работу в зарубежной компании, где команды часто говорят на русском
> - [Промпт для оформления профиля LinkedIn](https://t.me/just_solve_it_bot?start=u=2077531-s=3847197) — за 15 минут оформите профиль так, чтобы вас сами находили рекрутеры
<!-- gg-cta:top:end -->

#### Содержание
* Многопоточность и асинхронность
* Структуры данных
* Garbage Collection

🏆 Правильных ответов: 13 из 15.

#### Q1. Что выведет программа?

```java
public class Main {
    public static void foo(Integer i) {
        System.out.println("foo(Integer)");
    }
    public static void foo(short i) {
        System.out.println("foo(short)");
    }
    public static void foo(long i) {
        System.out.println("foo(long)");
    }
    public static void foo(Object i) {
        System.out.println("foo(object)");
    }
    public static void foo(int... i) {
        System.out.println("foo(int...)");
    }
    public static void main (String[] args) {
    foo (10);
    }
}
```

- [x] foo(long)

#### Q2. Что будет выведено при исполнении данного кода?

```java
public class Main {
    static boolean foo(char a) {
        System.out.print(a);
        return true;
    }
    public static void main(String[] args) {
        int i = 0;
        for (foo('A'); foo('B') && (i<2); foo('C')){
            i++;
            foo('D');
        }
    }
}
```

- [x] ABDCBDCB

#### Q3. Каким будет результат выполнения данного кода?

```java
Integer a = 100;
Integer b = 100;
Integer c = 200;
Integer d = 200;
Integer e = Integer.valueOf(100);
Integer f = Integer.valueOf(200);
System.out.println(a==b);
System.out.println(c==d);
System.out.println(e==a);
System.out.println(f==c);
```

- [x] true false true false

#### Q4. Каков результат работы этого кода?

```java
public class SomeClass {
    static int i = 1;
}

public class ExceptionTest {
    public static void main(String[] args) {
        System.out.println(foo());
    }

    static int foo() {
        try {
            SomeClass someClass = null;
            return someClass.i;
        } catch (Exception e) {
            return 2;
        } catch (Throwable e) {
            return 3;
        } finally {
            return 4;
        }
    }
}
```

- [x] 4

#### Q5. У вас есть 10 потоков, которые одновременно обращаются к одному и тому же ресурсу - очереди задач, реализованной с помощью `BlockingQueue`. Вам необходимо реализовать механизм, который гарантирует, что не более 5 потоков одновременно могут обрабатывать задачи из очереди. Какой из следующих способов НЕ подходит для решения этой задачи?

- [x] Использовать `CountDownLatch` с начальным значением 5 и каждый раз перед получением задачи из очереди вызывать метод `await()` у `CountDownLatch`. Когда поток заканчивает обработку задачи, он вызывает `countDown()`
- [ ] Использовать `ExecutorService` с фиксированным размером пула потоков, равным 5, и запускать все потоки через этот пул
- [ ] Использовать `ReentrantLock` для блокировки доступа к очереди задач, а внутри блокировки проверять, не превышает ли количество обрабатывающих задач 5, и, если да, ждать освобождения блокировки
- [ ] Создать отдельный класс-посредник, который будет обрабатывать запросы на получение задач из очереди и запускать обработку задач только для 5 потоков одновременно
- [ ] Использовать `Semaphore` с начальным значением 5 и каждый раз перед получением задачи из очереди вызывать метод `acquire()` у семафора, а после обработки задачи — `release()`

#### Q6. Какая структура данных из перечисленных НЕ является lock-free?

- [x] Atomiclnteger

#### Q7. Что из перечисленных функциональных ограничений синхронизации в Java является ЛОЖЬЮ?

- [x] Volatile переменная гарантирует атомарность последовательности читать-модифицировать-читать

#### Q8. Какие структуры данных требуют, чтобы данные реализовывали интерфейс Comparable?

- [x] TreeMap

#### Q9. После продолжительной работы сервиса графики показали, что память постепенно растет. Вы попросили вашего напарника проинспектировать код на наличие утечки памяти. Через пару дней он пришел с результатом, что утечкой памяти является цикличная ссылка в коде класса реализации графа. Выглядит это следующим образом. Может ли это быть причиной утечки памяти? (в качестве GC используется ParallelGC).

```java
class Node {
    private Node edge = null;
    public Node getEdge() {
        return edge;
    }
    public void setEdge(Node edge) {
        this.edge = edge;
    }
}
public void createAndDelete() {
    final var node1 = new Node();
    final var node2 = new Node();

    node1.setEdge(node2);
    node2.setEdge(node1);
}
```

- [ ] Да. ParalleIGC не умеет работать с циклическими ссылками, поэтому каждый вызов метода createAndDelete() увеличивает количество неуничтожаемых объектов.
- [x] Нет. Данные объекты не аллоцируются на куче при такой логике и тем самым не вызывают утечку.
- [ ] Да. Так как у объектов с циклическими ссылками надо вызывать метод finalize() чтобы он очистился. Иначе GC не может их удалить.
- [ ] Да. Из за цикличности ссылок объекты не могут быть перемещены из молодого поколения в старое

#### Q10. Какой способ итерирования по коллекции ArrayList приведет к ConcurrentModificationException, если во время итерирования происходит модификация коллекции?
- [ ] Итератор и метод remove()
- [ ] ListIterator и метод remove()
- [ ] Цикл for с доступом по индексу
- [x] Цикл for-each
- [ ] Стримы и метод forEach()

#### Q11. Какой вариант инициализации переменной приведет к ошибке?
```java
class Box<T> {
    T value;
    public Box (T value) {
        this.value = value;
    }
}

public static void main(String[] args) {
    Box<? super String> b1 = new Box<> (123);
    Box<? extends String> b2 = new Box<>("123");
    Box<? extends Number> b3 = new Box<>(123);
    Box<? super Number> b4 = new Box<>(123L);
}
```

- [ ] b1
- [ ] b2
- [ ] b3
- [ ] b4
- [x] Никакий из перечиленных

#### Q13. Что выведет код?

```java
interface A {
    default void method() {
        System.out.println("A");
    }
}

interface B {
    default void method() {
        System.out.println("B");
    }
}

class C implements A, B {
}

public class Main {
    public static void main(String[] args) {
        new C().method();
    }
}
```

- [x] Ошибка компиляции

#### Q14. Что выведет код?

```java
import java.util.*;
import java.util.stream.*;
public class Test {
    public static void main(String[] args) {
        List<String> list = Arrays.asList("one", "two", "three");
        list.stream()
            .filter(s-> s.length() > 3)
            .map(String::toUpperCase)
            .forEach(System.out::print);
    }
}
```

- [x] THREE

#### Q15. Что выведет код?

```java
ByteBuffer buffer = ByteBuffer.allocate(10);
buffer.put((byte) 1);
buffer.put((byte) 2);
buffer.flip();

System.out.print(buffer.get());
System.out.print(" ");
System.out.println(buffer.get());
```
- [ ] 1 1
- [ ] 2 1
- [ ] 2 2
- [ ] 258 0
- [x] 1 2

#### Q16. Какая гарантия отсутствует в volatile?
- [ ] Видимость изменений для других потоков
- [ ] Отношение happens-before между записью и последующими чтениями
- [ ] Консистентные обновления для всех потоков
- [ ] Предотвращение переупорядочивания инструкций
- [x] Атомарность инкремента (x++)

<!-- gg-cta:bottom:start -->

---

### Что еще пригодится в поиске работы

- **[500+ зарубежных IT-компаний с русскоязычными корнями](https://t.me/just_solve_it_bot?start=u=2077530-s=3948364)** — найдите работу в зарубежной компании, где команды часто говорят на русском.
- **[Промпт для профиля LinkedIn](https://t.me/just_solve_it_bot?start=u=2077531-s=3847197)** — за 15 минут оформите профиль так, чтобы вас сами находили рекрутеры.

Оба материала бесплатные, из канала [«Серёга, разберись!» @just_solve_it](https://t.me/+U3ZQerRYaNJiNWY6). Канал — о том, как айтишнику выйти на международный рынок с оффером 5000+$
<!-- gg-cta:bottom:end -->
