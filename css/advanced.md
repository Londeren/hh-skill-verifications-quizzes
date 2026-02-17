## CSS — продвинутый уровень

#### Содержание

- Трансформация: 2D и 3D
- Отзывчивый дизайн
- Позиционирование

#### С помощью какого селектора можно выбрать элементы с классами `d` и `f`?

```html
<div class="a">
  <div class="b">
    <p class="c">text</p>
  </div>
  <div class="d">
    <p class="e">text</p>
  </div>
  <div class="f">
    <span class="g">Text</span>
    <div class="h">Text</div>
  </div>
</div>
```

- [ ] .a > div
- [ ] div > div
- [x] div + div
- [ ] .d .f
- [ ] div.d.f

#### Как убрать подчеркивание у всех ссылок?

- [x] body \* { text-decoration: none; }
- [ ] body + \* { text-decoration: none; }
- [ ] body > \* { text-decoration: none !important; }
- [ ] body { text-decoration: none; }
- [ ] html { text-decoration: none !important; }

#### Как добавить логотип (размеры исходного изображения 40 × 40 пикселей) на страницу через тег img для адаптивной верстки?

- [ ] Дополнительных действий совершать не нужно
- [x] Ограничить ширину и высоту
- [ ] Сделать `img` блочным тегом
- [ ] Сделать `img` строчным тегом
- [ ] Задать `flex-basis`

#### Какой способ подключения CSS следует использовать, если нужно применять одни и те же стили к нескольким HTML-страницам в проекте?

- [ ] Применять JavaScript для динамического добавления CSS-правил в момент загрузки страницы.
- [ ] Использовать тег `<meta>` с атрибутом name, чтобы указать стили через мета-информацию страницы.
- [ ] Использовать атрибут `<style>` внутри каждого HTML-тега, прописывая стили для каждого элемента.
- [ ] Выставлять стили в каждом HTML-файле внутри тега `<style>`, для редактирования в коде страницы.
- [x] Подключить внешний CSS-файл с помощью выделенного тега `<link>` внутри секции `<head>`.

#### Как поменять значение padding для всех ссылок, если padding задавался через rem?

И теперь нужно изменить это значение padding для всех ссылок. Поскольку rem зависит от `font-size` корневого элемента `(html)`, правильный способ изменить значение `padding`, заданное в `rem`, — это либо:

1. Изменить `font-size` корневого элемента `(html)`, чтобы все значения rem на странице пересчитались. Это повлияет на `padding` ссылок, а также на все остальные элементы, использующие `rem`.
2. Переопределить `padding` для ссылок напрямую, задав новое значение (например, в `rem`, `px` или других единицах).
3. Наиболее правильный и эффективный способ изменить значение `padding` для всех ссылок, если оно задано в `rem`, — это изменить `font-size` корневого элемента `(html)`. Это повлияет на все значения rem на странице, включая padding ссылок. Например:

```css
html {
  font-size: 20px; /* Увеличиваем базовый размер шрифта, чтобы увеличить padding ссылок */
}
```

- [x] Изменить `font-size` у `body`
- [ ] Изменить `font-size` у каждой ссылки
- [ ] Написать `padding` в тег `html`, все ссылки унаследуют `padding`
- [ ] Изменить `font-size` у каждого непосредственного родителя каждой ссылки
- [ ] Написать `padding` в тег `body`, все ссылки унаследуют `padding`

#### Как расположить элементы в таком виде?

- [x] Использовать `display: flex; gap: 5%;` и задать последнему элементу `flex-basis: 50%`, чтобы он занял половину контейнера.
- [ ] Задать `display: flex` и регулировать расстояния между объектами через column-gap и row-gap.
- [ ] Использовать `display: flex` и управлять отступами с помощью margin для точной настройки положения элементов.
- [ ] Применить `display: flex; justify-content: stretch`, чтобы растягивать элементы по ширине без контроля.
- [ ] Установить `display: flex` и добавить третьему элементу `flex-grow: 1`, для заполнения всего доступного пространства.

#### Выберите верное утверждение

- [ ] Флексбокс требует больше кода и сложнее в использовании, чем традиционные методы разметки с использованием float и позиционирования.
- [ ] Не все современные браузеры поддерживают флексбокс.
- [ ] Флексбокс обеспечивает только горизонтальное выравнивание элементов.
- [ ] Флексбокс не позволяет переносить элементы на несколько строк.
- [x] Флексбокс не умеет создавать двумерные сетки.

#### Создать зеленую декоративную линию, разделяющую название страницы и текст, используя только CSS, можно сделать через

- [ ] box-shadow
- [ ] after
- [ ] stroke
- [ ] outline
- [x] border-bottom

#### Псевдоклассы в CSS позволяют стилизовать элементы в зависимости от их состояния. Какой из перечисленных селекторов используется для изменения стиля ранее открытых пользователем ссылок?

- [ ] a:active
- [ ] a:checked
- [x] a:visited
- [ ] a:enabled
- [ ] a:blank

#### Как реализовать функцию reduce motion для выключения всех анимаций и переходов на странице, используя @keyframes и CSS?

- [ ] { transition-property: none; animation: none !important; }
- [ ] { transition-timing-function: ease; animation: none; }
- [ ] { transition-delay: 0 !important; animation: none; }
- [ ] { transition-duration: 0; animation: none; }
- [x] { transition-duration: 0 !important; animation: none !important; }

#### Как можно создать 3D-эффект переворота карточки по оси X с помощью трансформации в CSS?

- [ ] transform: scale3d(1, 0, 0)
- [ ] transform: skew(360deg)
- [x] transform: rotateX(360deg)
- [ ] transform: matrix3d(360, 360, 360, 360)
- [ ] transform: perspective(360px)

#### Выберите вариант с лучшей производительностью позиционирования

- [ ] display: block
- [x] transform: translate(20px)
- [ ] position: sticky
- [ ] position: absolute; left: 100px
- [ ] position: fixed; right: 0px

#### Выберите вариант с наименьшим весом селекторов (приоритетом)

- [ ] p.sample#test
- [ ] p.test#test
- [ ] .text.sample.test
- [ ] p#test.sample
- [x] p.text.sample

#### Как прижать footer к низу экрана без появления вертикальной прокрутки?

```html
<style>
  * {
    margin: 0;
    padding: 0;
  }
  body {
    height: 100vh;
  }
</style>

<body>
  <header class="header">header</header>
  <main class="main">main</main>
  <footer class="footer">footer</footer>
</body>
```

- [ ] .footer { transform: translateY(100%) }
- [ ] .main { height: max-content; } и .footer { height: min-content; }
- [x] body { display: flex; flex-direction: column} и .main { flex-grow: 1 }
- [ ] .main { height: 100%; }
- [ ] .footer { position: absolute; top: 100%; width: 100% }

#### Что произойдет с карточкой, если ширина экрана будет меньше, чем 1200px?

```css
.card {
  width: 1200px;
  height: 600px;
  background-color: slateblue;
}
@media (width: 1200px) {
  .card {
    background-color: peachpuff;
    transition: all 0.3s ease 0s;
  }
}
```

- [ ] Карточка изменит цвет
- [ ] Запустится анимация
- [ ] Карточка будет пропорционально уменьшаться по ширине и высоте
- [ ] Карточка будет менять только свою ширину в зависимости от ширины экрана
- [x] Карточка не изменится

#### Как выбрать все `<span>`, находящиеся внутри элементов с двумя классами одновременно: `.f` и `.g`?

```html
<div class="f g">
  <span class="x">Text</span>
</div>
<div class="f">
  <span class="g">Another</span>
</div>
```

- [x] .f.g span
- [ ] .f + .g span
- [ ] .f .g span
- [ ] span.f.g
- [ ] span [class*=".f .g"]

#### Что произойдет с блочным элементом, если ему задать `width: auto`, `margin-left: auto` и `margin-right: auto`?

- [x] Растянется на всю ширину и прижмется к правому краю
- [ ] Скроется из зоны видимости
- [ ] Станет строчным элементом
- [ ] Выровняется по центру родителя по горизонтали
- [ ] Перестанет участвовать в потоке

#### В каком случае предпочтительно использовать тег `<style>` внутри секции `<head>`?

- [x] Когда стили специфичны для данной страницы и не предполагается их повторное использование
- [ ] Когда все стили хранятся во внешнем CDN и не требуется локальное хранение
- [ ] Когда необходимо обеспечить максимальную производительность за счёт кэширования
- [ ] Когда важна полная изоляция компонентов в SPA-приложении
- [ ] Когда проект использует SCSS и CSS должен быть скомпилирован на лету

#### Как повлиять на `vh`-высоту секции, если на мобильных устройствах часть `viewport` скрыта (например, адресная строка)?

- [ ] Использовать высоту в `рх` и добавить `overflow: auto`
- [x] Использовать `dvh` вместо `vh`
- [ ] Использовать `max-height: 100vh` u `padding: 10vh`
- [ ] Использовать `calc (100vh - 50px)` без учёта видимой области
- [ ] Использовать `min-height: 100%` k `<body>` и `<html>`

#### Как с помощью Flexbox расположить элементы в строку с индивидуальными отступами между ними?

- [ ] Использовать `display: flex; gap: 5%` и задать последнему элементу `flex-basis: 50%`, чтобы он занял половину контейнера
- [ ] Применить `display: flex; justify-content: stretch`, чтобы растягивать элементы по ширине без контроля
- [] Задать `display: flex` и регулировать расстояния между объектами через `column-gap` и `row-gap`
- [x] Использовать `display: flex` и управлять отступами с помощью `margin` для точной настройки положения элементов
- [ ] Установить `display: flex` и добавить третьему элементу `flex-grow: 1`, для заполнения всего доступного пространства

#### Какое из следующих утверждений отражает ограничения CSS Flexbox по сравнению с другими методами компоновки?

- [ ] Flexbox требует явного указания координат каждого элемента
- [ ] Flexbox не поддерживает автоматическое распределение свободного пространства
- [x] Flexbox не предназначен для построения сложных двумерных макетов
- [ ] Flexbox ограничен только вертикальной раскладкой элементов
- [ ] Flexbox несовместим c media queries

#### Как добавить иконку после текста кнопки без изменения HTML-разметки?

- [ ] Задать `::marker` содержимое
- [ ] Применить `:focus-visible`
- [ ] Использовать `::before` без `content`
- [ ] Применить `:has()` к кнопке
- [x] Добавить `::after` + `content`

#### Какой из следующих CSS-селекторов выберет каждый чётный элемент списка `<li>`, при этом начиная с нуля?

- [ ] `li:nth-of-type(odd)`
- [ ] `li:nth-last-child (2n)`
- [x] `li:nth-child(even)`
- [ ] `li:nth-child (2n+1)`
- [ ] `li:nth-child(odd)`

#### Как реализовать бесконечное вращение иконки с постоянной скоростью?

- [ ] `@keyframes infinite-spin { transform: Odeg to 360deg; } icon { animation: infinite-spin infinite; }`
- [ ] `icon { animation: spin ease infinite 1s; }`
- [ ] `@keyframes rotate { 100% { rotate: 360deg; } } icon { animation: rotate linear infinite; }`
- [x] `@keyframes spin { to { transform: rotate(360deg); } } icon { animation: spin 1s linear infinite; }`
- [ ] `icon { transition: transform 1s infinite; }`

#### Какой набор CSS-свойств нужен для того, чтобы два элемента располагались как передняя и задняя сторона 3D-карточки и анимировались при перевороте по оси Y?

- [ ] `transform: scale3d(1, 1, 0), perspective: 0`
- [ ] `transform: translateZ(200px), transform: rotateZ (180deg)`
- [ ] `transform: skewY(180deg), transform-style: preserve-3d`
- [ ] `transform-style: flat, transform: scale(2), backface-visibility: visible`
- [x] `transform-style: preserve-3d, backface-visibility: hidden, transform: rotateY(180deg)`

#### Какой метод позиционирования наиболее затратный по производительности при прокрутке страницы?

- [x] `position: sticky`
- [ ] `display: block`
- [ ] `position: static`
- [ ] `display: flex`
- [ ] `position: relative`

#### Какой из селекторов имеет наибольшую специфичность?

`<div class="item active" id="unique"></div>`

- [ ] `div#unique`
- [x] `.active#unique`
- [ ] `.item.active`
- [ ] `#unique`
- [ ] `div.item`

#### Как правильно сделать так, чтобы содержимое блока не выходило за границы экрана и появлялся скролл только по горизонтали?

```css
.wrapper {
  ???;
}
```

- [ ] `overflow: hidden`
- [ ] `overflow: auto; width: 100vw;`
- [ ] `scroll-behavior: smooth; overflow: visible;`
- [ ] `text-overflow: ellipsis; overflow: auto;`
- [x] `overflow-x: scroll; white-space: nowrap;`
