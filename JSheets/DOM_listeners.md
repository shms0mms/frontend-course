# Шпаргалка: DOM События

---

## Что такое события?
События — это сигналы, которые генерируются в браузере при взаимодействии пользователя или других действиях (например, клики, нажатие клавиш, загрузка страницы).

---

## Основные виды событий

| **Тип события**        | **Примеры**                                                                       |
| ---------------------- | --------------------------------------------------------------------------------- |
| **События мыши**       | `click`, `dblclick`, `mousedown`, `mouseup`, `mousemove`, `mouseover`, `mouseout` |
| **События клавиатуры** | `keydown`, `keypress`, `keyup`                                                    |
| **События ввода**      | `input`, `change`, `focus`, `blur`                                                |
| **События документа**  | `DOMContentLoaded`, `scroll`, `resize`, `error`                                   |
| **События формы**      | `submit`, `reset`                                                                 |

---

## Назначение обработчиков событий

1. **Через атрибут HTML** (не рекомендуется):
```html
<button onclick="alert('Привет!')">Кликни меня</button>
```

2. **Через свойство объекта**:
```js
const button = document.querySelector('button');
button.onclick = () => alert('Клик!');
```

3. **Через `addEventListener()`** (рекомендуется):
```js
const button = document.querySelector('button');
button.addEventListener('click', () => alert('Клик!'));
```

---

## Методы работы с событиями

### 1. **`addEventListener`**
- Используется для добавления событий.
- Позволяет добавлять несколько обработчиков к одному элементу.
- Синтаксис:
```js
element.addEventListener(event, handler, options);
```
  - `event`: тип события (`click`, `input`, и т.д.).
  - `handler`: функция-обработчик.
  - `options`: необязательный объект с настройками (например, `once`, `capture`).

Пример:
```js
button.addEventListener('click', () => alert('Первый обработчик'));
button.addEventListener('click', () => alert('Второй обработчик'));
```

### 2. **`removeEventListener`**
- Удаляет ранее добавленный обработчик.
- Синтаксис:
```js
element.removeEventListener(event, handler);
```
Пример:
```js
const handler = () => alert('Клик!');
button.addEventListener('click', handler);
button.removeEventListener('click', handler);
```

---

## Особенности событий

1. **Всплытие (Bubbling)**:
   - Событие сначала происходит на самом глубоком элементе, затем поднимается вверх по дереву.
   - Пример:
```html
<div>
  <button>Кликни</button>
</div>
```

```js
document.querySelector('div').addEventListener('click', () => alert('DIV!'));
document.querySelector('button').addEventListener('click', () => alert('BUTTON!'));
```
При клике на кнопку: сначала выведется `BUTTON!`, затем `DIV!`.

2. **Захват (Capturing)**:
   - Обратный процесс: событие проходит сверху вниз.
   - Для включения захвата используется третий параметр в `addEventListener()`:
```js
element.addEventListener('click', handler, { capture: true });
```

3. **Остановка всплытия**:
   - Используйте `event.stopPropagation()`:
```js
button.addEventListener('click', (event) => {
  event.stopPropagation();
  alert('Только кнопка!');
});
```

---

## Частые события и их особенности

### **`click`**
- Вызывается при клике мышью.
- Можно использовать для кнопок, ссылок, интерактивных элементов.

### **`input`**
- Срабатывает при изменении значения поля ввода (текстового, числового и т.д.).

### **`keydown` и `keyup`**
- `keydown`: вызывается при нажатии клавиши.
- `keyup`: вызывается при отпускании клавиши.
- Пример:
```js
document.addEventListener('keydown', (event) => {
  console.log(`Нажата клавиша: ${event.key}`);
});
```

### **`submit`**
- Срабатывает при отправке формы.
- Часто используется с `event.preventDefault()`, чтобы предотвратить перезагрузку страницы:
```js
form.addEventListener('submit', (event) => {
  event.preventDefault();
  console.log('Форма отправлена!');
});
```

---

## Работа с объектом события (`event`)

### Основные свойства:
| **Свойство**         | **Описание**                                                   |
|----------------------|---------------------------------------------------------------|
| `target`             | Элемент, на котором произошло событие                         |
| `currentTarget`      | Элемент, на котором установлен обработчик                     |
| `type`               | Тип события (например, `click`, `input`)                      |
| `timeStamp`          | Время, когда событие произошло                                |
| `key`                | Клавиша, которая была нажата (для событий клавиатуры)         |
| `clientX`, `clientY` | Координаты курсора относительно окна                          |
| `preventDefault()`   | Отменяет действие по умолчанию (например, переход по ссылке)  |
| `stopPropagation()`  | Останавливает всплытие события                                |

--- 

## Полезные опции в `addEventListener`

| **Опция**  | **Описание**                                                   |
|------------|---------------------------------------------------------------|
| `once`     | Обработчик выполнится только один раз                          |
| `capture`  | Событие обрабатывается на стадии захвата                       |
| `passive`  | Улучшает производительность для скроллинга (запрещает `preventDefault`) |

Пример:
```js
element.addEventListener('click', handler, { once: true });
```

