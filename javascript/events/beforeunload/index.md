---
metaTitle: Событие beforeunload в JavaScript
metaDescription: Разбираемся как работает событие beforeunload в JavaScript
author: Дмитрий Нечаев
title: Событие beforeunload в JavaScript
preview: Учимся пользоваться событием beforeunload в JavaScript. Разбираем примеры использования
---

Событие `beforeunload` в JavaScript срабатывает непосредственно перед тем, как пользователь покидает веб-страницу. Это может происходить при закрытии вкладки, переходе на другой URL или перезагрузке страницы. Событие дает возможность запросить подтверждение у пользователя о намерении покинуть страницу, а также выполнить необходимые действия для сохранения данных или состояния работы. Эта статья рассмотрит использование `beforeunload` для улучшения пользовательского опыта и предотвращения потери данных.

### Как работает событие "beforeunload"?

Событие `beforeunload` привязывается к объекту `window` и может использоваться для отображения стандартного диалогового окна браузера, в котором пользователю предлагается подтвердить свое намерение покинуть страницу. Вы можете установить текст предупреждения, однако большинство современных браузеров по умолчанию игнорируют пользовательский текст в диалоговом окне по соображениям безопасности и используют стандартное сообщение.

### Пример использования события "beforeunload"

### Предупреждение пользователя о возможной потере данных

```jsx
window.addEventListener('beforeunload', function(event) {
    // Проверяем, есть ли несохраненные изменения
    if (formIsDirty) {
        // Стандартный текст будет проигнорирован большинством браузеров
        const message = 'На странице остались несохраненные изменения. Вы уверены, что хотите уйти?';
        event.returnValue = message; // Необходимо для Chrome
        return message; // Необходимо для некоторых других браузеров
    }
});

```

В этом коде, если в форме есть несохраненные изменения, пользователю будет предложено подтверждение на уход со страницы. `event.returnValue` должно быть установлено для обеспечения совместимости с различными браузерами.

### Особенности и рекомендации использования "beforeunload"

1. **Использование для важных предупреждений**: Используйте `beforeunload` только в случаях, когда действительно необходимо предотвратить потерю данных (например, при работе с онлайн-формами или редакторами).
2. **Ограничения на кастомизацию сообщений**: Браузеры не позволяют кастомизировать текст в диалоговом окне `beforeunload` для предотвращения мошенничества, поэтому пользователи увидят стандартное сообщение.
3. **Не злоупотреблять этим событием**: Частое использование `beforeunload` может негативно сказаться на пользовательском опыте, так как прерывает естественный процесс навигации по сайту.

### Заключение

Событие `beforeunload` является мощным инструментом в руках веб-разработчиков, позволяющим предотвратить потерю важных данных пользователем. Важно использовать это событие с умом, чтобы не создать лишние неудобства для пользователей. Правильно настроенное событие `beforeunload` может значительно повысить удобство и безопасность пользовательских данных при работе с веб-приложениями.