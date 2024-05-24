---
metaTitle: Специфичность в CSS
metaDescription: Специфичность в CSS
author: Дмитрий Нечаев
title: Специфичность в CSS. Полное руководство с примерами
preview: Специфичность (или вес селектора) — это механизм, который позволяет браузеру определить, какое правило CSS более приоритетное, когда к одному элементу применяются несколько правил.
---

В процессе разработки веб-страниц с использованием CSS часто возникает вопрос: как браузер решает, какие стили применять к элементу, если для него определено несколько правил? Ответ на этот вопрос заключается в понятии **специфичности**. Специфичность (или вес селектора) — это механизм, который позволяет браузеру определить, какое правило CSS более приоритетное, когда к одному элементу применяются несколько правил.

## Как рассчитывается специфичность?

Специфичность определяется на основе четырёх компонентов: селекторов тегов, классов, идентификаторов и встроенных стилей. Каждому из этих компонентов присваивается определённое количество баллов, которые затем суммируются для определения общей специфичности.

### Правила подсчёта специфичности

1. **Селекторы тегов и псевдоэлементы** (например, `div`, `p`, `::before`) — 1 балл за каждый.
2. **Селекторы классов, атрибутов и псевдоклассы** (например, `.class`, `[type="text"]`, `:hover`) — 10 баллов за каждый.
3. **Селекторы идентификаторов** (например, `#id`) — 100 баллов за каждый.
4. **Встроенные стили** (например, `style="..."`) — 1000 баллов за каждый.

### Пример подсчёта специфичности

Рассмотрим несколько примеров селекторов и их специфичность:

1. `div` — 1 балл (один селектор тега)
2. `.class` — 10 баллов (один селектор класса)
3. `#id` — 100 баллов (один селектор идентификатора)
4. `div.class` — 11 баллов (один селектор тега и один селектор класса)
5. `#id.class` — 110 баллов (один селектор идентификатора и один селектор класса)
6. `style="color: red;"` — 1000 баллов (встроенный стиль)

## Как браузер выбирает стили?

Когда браузер сталкивается с несколькими правилами, применимыми к одному элементу, он использует специфичность для определения приоритета каждого правила. Чем выше специфичность, тем выше приоритет.

### Пример применения специфичности

Рассмотрим HTML-элемент и несколько CSS-правил для него:

```html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    div {
      color: blue;
    }

    .example {
      color: green;
    }

    #unique {
      color: red;
    }
  </style>
  <title>Специфичность</title>
</head>
<body>
  <div id="unique" class="example">Текст</div>
</body>
</html>

```

В этом примере к элементу `<div>` применяются три правила:

1. `div { color: blue; }` — специфичность 1.
2. `.example { color: green; }` — специфичность 10.
3. `#unique { color: red; }` — специфичность 100.

Браузер выберет правило с наивысшей специфичностью, то есть `#unique { color: red; }`. Таким образом, текст будет красного цвета.

## Важные нюансы

### Влияние порядка правил

Если два правила имеют одинаковую специфичность, то применяется последнее из них в порядке определения. Рассмотрим пример:

```css
p {
  color: blue;
}

p {
  color: green;
}

```

Оба правила имеют одинаковую специфичность (1 балл), но второе правило перекроет первое, и текст будет зелёного цвета.

### Вложенные селекторы

Вложенные селекторы увеличивают специфичность. Рассмотрим пример:

```css
body div p {
  color: blue;
}

```

Этот селектор имеет специфичность 3 (один тег `body`, один тег `div` и один тег `p`).

### !important

Свойство `!important` позволяет принудительно применить стиль, игнорируя специфичность. Пример:

```css
p {
  color: blue !important;
}

p {
  color: green;
}

```

Несмотря на то, что второе правило определено позже, текст будет синим из-за `!important`.

## Заключение

Специфичность — это ключевая концепция CSS, которая помогает браузеру решать, какие стили применять к элементам на странице. Понимание специфичности позволяет разработчикам создавать более точную и управляемую верстку, избегая конфликтов стилей и неожиданного поведения элементов. Важно учитывать специфичность при написании CSS, чтобы уверенно управлять внешним видом веб-страниц.