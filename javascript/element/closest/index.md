---
metaTitle: .closest() в JavaScript
metaDescription: Разбираемся как использовать .closest() в JavaScript
author: Дмитрий Нечаев
title: .closest() в JavaScript
preview: Учимся пользоваться .closest() в JavaScript. Разбираем примеры использования
---

Метод `.closest()` в JavaScript позволяет нам получить ближайший родительский элемент, который соответствует заданному CSS-селектору. Это очень полезно, когда мы хотим найти определенный родительский элемент относительно текущего элемента, особенно когда у нас есть вложенные структуры в HTML. В этой статье мы рассмотрим, как использовать `.closest()` и какие возможности он предоставляет.

## Введение в `.closest()`

Метод `.closest()` - это метод, доступный для DOM-элементов, который позволяет нам получить ближайший родительский элемент, удовлетворяющий заданному CSS-селектору. Этот метод осуществляет поиск родительских элементов, начиная с текущего элемента и двигаясь вверх по DOM-дереву. Как только он находит элемент, удовлетворяющий селектору, поиск останавливается, и этот элемент возвращается.

Синтаксис `.closest()` выглядит следующим образом:

```jsx
element.closest(selector);

```

Где:

- `element` - это DOM-элемент, относительно которого мы хотим начать поиск родительского элемента.
- `selector` - это строка, представляющая CSS-селектор, по которому нужно выполнить поиск родительского элемента.

## Примеры использования `.closest()`

Давайте рассмотрим несколько примеров использования метода `.closest()` для поиска родительского элемента по заданному CSS-селектору.

### 1. Нахождение родительского элемента с определенным классом

```html
<div class="container">
  <div class="item">
    <button>Кнопка</button>
  </div>
</div>

```

```jsx
// Находим кнопку
const button = document.querySelector('button');

// Находим ближайший родительский элемент с классом "container"
const container = button.closest('.container');

// Добавляем стиль к найденному родительскому элементу
container.style.border = '2px solid red';

```

В этом примере мы находим кнопку, а затем с помощью `.closest()` находим ближайший родительский элемент с классом "container" и добавляем ему стиль.

### 2. Нахождение родительского элемента по тегу

```html
<div>
  <p>Первый абзац</p>
  <div>
    <span>Это спан</span>
  </div>
</div>

```

```jsx
// Находим спан
const span = document.querySelector('span');

// Находим ближайший родительский элемент <div>
const div = span.closest('div');

// Добавляем стиль к найденному родительскому элементу
div.style.backgroundColor = 'lightblue';

```

В этом примере мы находим спан, а затем с помощью `.closest()` находим ближайший родительский элемент `<div>` и добавляем ему стиль.

### 3. Нахождение родительского элемента по id

```html
<div id="parent">
  <div id="child">
    <p>Этот параграф находится внутри дочернего элемента</p>
  </div>
</div>

```

```jsx
// Находим параграф
const paragraph = document.querySelector('p');

// Находим ближайший родительский элемент с id "parent"
const parentDiv = paragraph.closest('#parent');

// Добавляем стиль к найденному родительскому элементу
parentDiv.style.border = '2px solid green';

```

В этом примере мы находим параграф, а затем с помощью `.closest()` находим ближайший родительский элемент с id "parent" и добавляем ему стиль.

## Заключение

Метод `.closest()` является мощным инструментом для нахождения ближайшего родительского элемента, который соответствует заданному CSS-селектору. Это удобно для управления и манипуляции элементами в комплексных и вложенных структурах DOM.