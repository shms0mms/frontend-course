

DOM (Document Object Model) — это программная модель, представляющая HTML-документ в виде дерева объектов. Каждый элемент страницы (тег, атрибут, текст) представлен узлом в дереве DOM. С помощью методов и свойств DOM можно динамически манипулировать содержимым веб-страницы.

# Основные методы и свойства DOM

1. **document**
    - Глобальный объект, представляющий весь документ. Через него можно получить доступ к различным элементам страницы.
2. **querySelector()**
    - Метод для поиска первого элемента, соответствующего указанному селектору CSS. Например:
        

```javascript
const element = document.querySelector('.my-class');
```

- **classList**
    - Свойство, позволяющее управлять классами элемента. Оно предоставляет удобные методы для добавления, удаления и переключения классов:
        - `element.classList.add('new-class')` — добавление класса.
        - `element.classList.remove('old-class')` — удаление класса.
        - `element.classList.toggle('toggle-class')` — переключение класса (если класс отсутствует, добавляется, если присутствует — удаляется).

- **getElementById()**
    - Позволяет получить элемент по его уникальному идентификатору (ID):
        

```javascript
const myElement = document.getElementById('unique-id');
```

**createElement()**

- Создает новый элемент в документе:
    

```javascript
const newDiv = document.createElement('div');
newDiv.textContent = 'Новый элемент';
document.body.appendChild(newDiv);
```

**appendChild()**

- Добавляет дочерний узел в конец списка дочерних узлов родительского узла:
    

```javascript
parentElement.appendChild(childElement);
```

**removeChild()**

- Удаляет указанный дочерний элемент из родительского:
    

```javascript
parentNode.removeChild(childNode);
```

**innerHTML**

- Содержимое элемента в виде HTML-кода. Может быть использовано для изменения содержимого элемента:
    

```javascript
element.innerHTML = '<p>Новое содержимое</p>';
```

# Пример использования

Допустим, у нас есть следующая HTML-разметка:

```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Пример работы с DOM</title>
</head>
<body>
    <h1 id="header">Заголовок</h1>
    <button onclick="changeHeader()">Изменить заголовок</button>
    <script src="script.js"></script>
</body>
</html>
```

А вот соответствующий JavaScript-код (`script.js`):

```javascript
function changeHeader() {
    const header = document.getElementById('header');
    header.textContent = "Обновленный заголовок";
    header.classList.toggle('highlighted');
}
```

При нажатии на кнопку «Изменить заголовок» текст заголовка изменится, и ему будет добавлен или убран класс `highlighted`.

Таким образом, используя методы и свойства DOM, вы можете легко манипулировать элементами веб-страниц, добавлять новые элементы, удалять существующие и изменять их внешний вид и поведение.