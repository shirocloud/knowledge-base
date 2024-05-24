---
metaTitle: rem и em в CSS. Относительные единицы измерения от размера шрифта
metaDescription: rem и em в CSS. Относительные единицы измерения от размера шрифта
author: Дмитрий Нечаев
title: rem и em в CSS. Полное руководство с примерами
preview: В CSS существуют различные единицы измерения для задания размеров элементов. Одними из наиболее часто используемых являются относительные единицы rem и em, которые зависят от размера шрифта.
---

В CSS существуют различные единицы измерения для задания размеров элементов. Одними из наиболее часто используемых являются относительные единицы `rem` и `em`, которые зависят от размера шрифта. Эти единицы измерения позволяют создавать гибкие и адаптивные дизайны, облегчая управление стилями. В этой статье мы рассмотрим, как работают `rem` и `em`, приведём примеры их использования и обсудим преимущества каждого метода.

## Что такое `rem` и `em`?

### `em`

Единица измерения `em` основывается на размере шрифта родительского элемента. 1em равен текущему размеру шрифта элемента. Если размер шрифта родительского элемента изменится, то и значение `em` изменится соответственно.

### Пример использования `em`

```css
.parent {
    font-size: 16px;
}

.child {
    font-size: 2em; /* 2em = 2 * 16px = 32px */
    padding: 1em; /* 1em = 16px */
}

```

В этом примере элемент с классом `child` наследует размер шрифта от родителя (`16px`) и задаёт свой размер шрифта как `2em`, что эквивалентно `32px`. Отступы элемента также будут равны `16px` (1em).

### `rem`

Единица измерения `rem` основывается на размере шрифта корневого элемента (`html`). 1rem всегда равен значению, установленному для `font-size` элемента `html`, что делает `rem` более предсказуемой и универсальной единицей.

### Пример использования `rem`

```css
html {
    font-size: 16px;
}

.element {
    font-size: 2rem; /* 2rem = 2 * 16px = 32px */
    margin: 1rem; /* 1rem = 16px */
}

```

В этом примере размер шрифта элемента с классом `element` будет равен `32px` (2rem), а отступы — `16px` (1rem), основываясь на значении `font-size` корневого элемента (`html`).

## Преимущества использования `rem` и `em`

### Гибкость и адаптивность

Использование `em` и `rem` позволяет создавать гибкие и адаптивные макеты, которые легко подстраиваются под изменения размера шрифта. Это особенно полезно для создания доступных интерфейсов, где пользователи могут изменять размер текста.

### Удобство управления стилями

Эти единицы измерения облегчают управление стилями, особенно в крупных проектах. Изменение размера шрифта корневого элемента (`html`) или родительского элемента автоматически обновит все связанные элементы, что упрощает процесс масштабирования.

### Поддержка типографики

Использование `em` и `rem` помогает поддерживать пропорциональность и консистентность типографики на сайте, обеспечивая единообразие размеров текста, отступов и других элементов.

## Примеры использования `rem` и `em` в различных контекстах

### Пример 1: Адаптивные размеры текста

```css
html {
    font-size: 16px;
}

h1 {
    font-size: 2rem; /* 32px */
}

p {
    font-size: 1rem; /* 16px */
}

```

### Пример 2: Адаптивные отступы и поля

```css
html {
    font-size: 16px;
}

.container {
    padding: 2rem; /* 32px */
    margin: 1rem; /* 16px */
}

.button {
    padding: 0.5rem 1rem; /* 8px 16px */
    font-size: 1rem; /* 16px */
}

```

### Пример 3: Использование `em` для внутренних элементов

```css
html {
    font-size: 16px;
}

.card {
    font-size: 1rem; /* 16px */
    padding: 1.5em; /* 24px */
}

.card-title {
    font-size: 1.5em; /* 24px */
}

.card-content {
    font-size: 1em; /* 16px */
}

```

В этом примере элементы внутри `.card` используют `em` для задания своих размеров относительно размера шрифта `.card`, что обеспечивает гибкость и согласованность.

## Когда использовать `rem`, а когда `em`?

### Использование `rem`

- Для глобальных размеров, таких как отступы и поля контейнеров.
- Для типографики, чтобы обеспечить согласованность размеров текста.
- Когда важно, чтобы размеры оставались предсказуемыми и неизменными независимо от иерархии элементов.

### Использование `em`

- Для внутренних отступов и размеров элементов, которые должны масштабироваться относительно родительского элемента.
- Когда необходимо создавать компоненты с размером, зависимым от контекста, в котором они находятся.
- Для создания вложенных элементов, размеры которых зависят от родительских.

## Заключение

Относительные единицы измерения `rem` и `em` предоставляют мощные инструменты для создания гибких и адаптивных дизайнов в CSS. Понимание их особенностей и правильное применение позволяет значительно упростить управление стилями и обеспечить согласованность макета на различных устройствах. Освоив использование `rem` и `em`, вы сможете создавать более масштабируемые и поддерживаемые веб-проекты, которые легко адаптируются к изменениям и обеспечивают лучший пользовательский опыт.