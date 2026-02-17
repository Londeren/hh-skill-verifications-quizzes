## CSS — базовый уровень

#### Содержание

- Селекторы
- Наследование
- Теги

#### Какой селектор выбирает элементы с классом text?

- [ ] text[class]
- [ ] text.
- [ ] class(text)
- [x] .text
- [ ] class. text

#### Выберите вариант, в котором селекторы расположены в порядке увеличения их приоритета.

- [ ] .text, p, #title
- [ ] p, #text, .text
- [ ] .text, #text, p
- [x] p, .text, #title
- [ ] #text, .text, p

#### Какой селектор применит стили ко всем < li> элементам, являющимся непосредственными детьми <ul> с классом menu?

- [ ] .menu li > ul
- [ ] li > ul.menu
- [ ] .menu > ul li
- [x] ul.menu > li
- [ ] ul.menu li

#### Выберите вариант ответа, в котором содержатся только наследуемые свойства.

- [x] color, font-family, line-height
- [ ] width, border, height
- [ ] border-radius, display, color
- [ ] font-family, color, background-color
- [ ] list-style-type, display, line-height

#### Как сократить запись одинаковых стилей для нескольких дочерних элементов?

- [ ] Применить селектор `.parent + .parent`
- [ ] Использовать псевдокласс `:empty`
- [ ] Использовать `display: inherit`
- [x] Группировать селекторы через запятую
- [ ] Писать каждый селектор отдельно

#### Какие HTML-элементы по умолчанию имеют `display: inline-block`?

- [x] img, button, input, select, textarea
- [ ] div, p, h1, section, article
- [ ] ul, ol, li, dl, dt
- [ ] table, tr, td, th, caption
- [ ] a, span, em, strong, b

#### Какой из способов позволяет надёжно предотвратить схлопывание нижнего `margin` дочернего элемента с верхним margin родительского элемента, не нарушая структуру потока?

- [ ] Применить `position: absolute` к дочернему элементу
- [ ] Назначить `display: inline` дочернему элементу
- [x] Добавить `padding-top `родительскому элементу
- [ ] Добавить `border-top` родителю
- [ ] Задать дочернему элементу `margin-bottom: 0`

#### Какой атрибут тега < link> указывает на местоположение файла CSS?

- [ ] type
- [x] href
- [ ] rel
- [ ] data
- [ ] src

#### Что нужно сделать, чтобы сместить элемент по горизонтали вправо ровно на свою ширину?

- [ ] `flex-basis: 100%`
- [x] `transform: translate (100%)`
- [ ] `left: 50%`
- [ ] `text-align: right`
- [ ] `right: 100%`
