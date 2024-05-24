---
metaTitle: Функция clamp в CSS. как задать минимальное и максимальное значения в одну строчку кода
metaDescription: Функция clamp в CSS. как задать минимальное и максимальное значения в одну строчку кода
author: Дмитрий Нечаев
title: Функция clamp в CSS. Полное руководство с примерами
preview: CSS предлагает множество возможностей для управления размером элементов на веб-страницах. Одной из полезных функций является clamp, которая позволяет задавать значения с минимальными и максимальными ограничениями в одну строчку кода.
---

CSS предлагает множество возможностей для управления размером элементов на веб-страницах. Одной из полезных функций является `clamp()`, которая позволяет задавать значения с минимальными и максимальными ограничениями в одну строчку кода. Это делает код более читабельным и управляемым. В этой статье мы подробно рассмотрим, как работает функция `clamp()`, и приведём примеры её использования.

## Основы функции `clamp()`

Функция `clamp()` позволяет задать значение, которое ограничено минимальным и максимальным пределами. Она принимает три аргумента:

1. Минимальное значение.
2. Предпочтительное значение.
3. Максимальное значение.

### Синтаксис функции `clamp()`

```css
property: clamp(minimum, preferred, maximum);

```

- `minimum` — минимальное значение.
- `preferred` — предпочитаемое значение.
- `maximum` — максимальное значение.

Функция `clamp()` гарантирует, что итоговое значение будет не меньше минимального и не больше максимального, но стремится к предпочитаемому значению.

### Пример базового использования `clamp()`

```css
.element {
    font-size: clamp(16px, 2vw, 24px);
}

```

В этом примере размер шрифта будет изменяться в зависимости от ширины окна просмотра, но не будет меньше 16 пикселей и не больше 24 пикселей.

## Преимущества использования `clamp()`

### 1. Простота и читабельность

Использование `clamp()` упрощает код и делает его более читабельным по сравнению с использованием медиазапросов и других методов для управления размерами.

### 2. Гибкость

Функция `clamp()` позволяет задать адаптивные значения, которые изменяются в зависимости от контекста, но при этом остаются в заданных пределах.

### 3. Управление сложными вычислениями

С `clamp()` можно легко управлять сложными вычислениями значений, используя арифметические операции и другие функции CSS.

## Примеры использования функции `clamp()`

### Пример 1: Адаптивный отступ

```css
.element {
    padding: clamp(10px, 5vw, 20px);
}

```

В этом примере отступ будет адаптироваться в зависимости от ширины окна, но не будет меньше 10 пикселей и не больше 20 пикселей.

### Пример 2: Ширина элемента

```css
.element {
    width: clamp(200px, 50%, 400px);
}

```

В этом примере ширина элемента будет изменяться от 200 пикселей до 400 пикселей, стремясь к 50% от ширины родительского элемента.

### Пример 3: Размер шрифта в заголовке

```css
h1 {
    font-size: clamp(24px, 4vw, 40px);
}

```

В этом примере размер шрифта заголовка будет адаптироваться в зависимости от ширины окна, но не будет меньше 24 пикселей и не больше 40 пикселей.

### Пример 4: Гибкий размер изображения

```css
img {
    height: clamp(100px, 20vw, 300px);
    width: clamp(100px, 20vw, 300px);
}

```

В этом примере размер изображения будет изменяться в зависимости от ширины окна, но останется в пределах от 100 до 300 пикселей.

## Сложные примеры использования `clamp()`

### Пример 5: Комплексный расчет ширины

```css
.element {
    width: clamp(200px, calc(100% - 2rem), 600px);
}

```

В этом примере ширина элемента будет адаптироваться, основываясь на выражении `calc(100% - 2rem)`, но не будет меньше 200 пикселей и не больше 600 пикселей.

### Пример 6: Вложенные элементы с адаптивными размерами

```css
.container {
    padding: clamp(1rem, 2vw, 3rem);
}

.container .item {
    margin: clamp(0.5rem, 1vw, 1.5rem);
}

```

В этом примере отступы контейнера и элементов внутри него будут адаптироваться в зависимости от ширины окна, но останутся в заданных пределах.

## Заключение

Функция `clamp()` в CSS предоставляет мощные возможности для управления размерами элементов, делая код более гибким и управляемым. С её помощью можно легко задавать значения, которые адаптируются к различным условиям, но остаются в пределах минимальных и максимальных значений. Освоив использование функции `clamp()`, вы сможете значительно улучшить процесс стилизации и адаптивного дизайна ваших веб-страниц.