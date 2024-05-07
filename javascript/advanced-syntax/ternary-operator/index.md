---
metaTitle: Тернарный оператор в JavaScript
metaDescription: Разбираемся как работает тернарный оператор в JavaScript
author: Дмитрий Нечаев
title: Тернарный оператор в JavaScript
preview: Учимся пользоваться тернарным оператором в JavaScript. Разбираем примеры использования
---

Тернарный оператор в JavaScript представляет собой альтернативный способ записи условных выражений с использованием конструкции `if...else`. Он позволяет выполнить одно из двух действий в зависимости от истинности или ложности условия.

### Синтаксис

```jsx
условие ? выражение1 : выражение2

```

Если условие истинно, то возвращается `выражение1`, если ложно - `выражение2`.

### Примеры

Рассмотрим примеры использования тернарного оператора:

```jsx
const age = 20;
const message = age >= 18 ? "Совершеннолетний" : "Несовершеннолетний";
console.log(message); // Выведет: "Совершеннолетний"

```

В этом примере, если возраст `age` больше или равен 18, будет возвращена строка "Совершеннолетний", иначе - "Несовершеннолетний".

### Вложенные тернарные операторы

Тернарные операторы могут быть вложенными для более сложных условий:

```jsx
const score = 75;
const result = score >= 50 ? (score >= 80 ? "Отлично" : "Хорошо") : "Неудовлетворительно";
console.log(result); // Выведет: "Хорошо"

```

В этом примере, если `score` больше или равен 50, тогда, если больше или равен 80 - "Отлично", иначе - "Хорошо". В противном случае - "Неудовлетворительно".

### Преимущества использования тернарного оператора

1. **Краткость кода:** Тернарный оператор позволяет сократить объем кода по сравнению с использованием конструкции `if...else`.
2. **Читаемость:** Он делает код более читаемым, особенно в случаях, когда условие и результат являются простыми.

### Заключение

Тернарный оператор - это удобный инструмент для написания компактных и читаемых условных выражений в JavaScript. Он позволяет сократить объем кода и повысить его читаемость, особенно в случаях, когда условия просты. Однако, следует быть осторожным с его использованием в случаях, когда условия слишком сложные, так как это может привести к уменьшению читаемости кода.