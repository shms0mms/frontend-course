
# WINDOW

```javascript
const windowWidth = window.innerWidth;
console.log(`Ширина окна браузера: ${windowWidth}px`);
````

---

# Navigator

С помощью объекта `navigator` можно получить информацию о браузере и операционной системе.

# Браузер

```javascript
console.log(navigator.userAgent);

if (navigator.userAgent.includes("Chrome")) {
    console.log('Браузер Хром');
} else if (navigator.userAgent.includes("Firefox")) {
    console.log('Браузер Firefox');
}
```

# Платформа

```javascript
console.log(navigator.platform);
```

---

# Location

С помощью объекта `location` можно получать текущий URL или перенаправлять браузер по новому адресу.

# Получение текущего URL

```javascript
console.log(location.href);
```

# Переход по новому URL

```javascript
location.href = "https://google.com";
```

---

# History

Объект `history` позволяет управлять историей браузера, перемещаясь между посещенными страницами.

# Перемещение назад

```javascript
history.back();
```

# Перемещение вперед

```javascript
history.forward();
```



---


# Навигация по документу

С помощью объекта `document` можно получить доступ к основным элементам документа.

### Верхние элементы дерева

```javascript
const htmlElement = document.documentElement;
const headElement = document.head;
const bodyElement = document.body;
console.log(htmlElement);
console.log(headElement);
console.log(bodyElement);
````

# Первый и последний дочерние элементы

```javascript
const bodyElement = document.body;
const firstChildNode = bodyElement.firstChild;
const lastChildNode = bodyElement.lastChild;
console.log(firstChildNode);
console.log(lastChildNode);
```

**Примечание:** Для корректной работы скриптов их рекомендуется размещать в конце документа, чтобы избежать ситуаций, когда браузер еще не обработал весь код.

# Коллекция childNodes

```javascript
const childNodes = bodyElement.childNodes;
console.log(childNodes);
```

Эта коллекция содержит список всех дочерних элементов, включая текстовые узлы. Чтобы проверить наличие дочерних узлов, используется метод `hasChildNodes()`:

```javascript
console.log(bodyElement.hasChildNodes());
```

# Перебор коллекции

```javascript
for (let node of childNodes) {
    console.log(node); // покажет все узлы из коллекции
}
```

# "Живые" коллекции

Большинство DOM-коллекций являются "живыми", т.е. они отражают текущее состояние DOM. Если сохранить ссылку на коллекцию и изменить структуру DOM, эти изменения сразу же отразятся в коллекции.

# Только для чтения

Все DOM-коллекции и навигационные свойства доступны только для чтения. Нельзя напрямую изменять содержимое коллекций, например, заменяя один дочерний узел другим. Для этого существуют специальные методы.

# Соседние и родительские узлы

```javascript
const previousSiblingNode = bodyElement.previousSibling;
const nextSiblingNode = bodyElement.nextSibling;
const parentNode = bodyElement.parentNode;

console.log(previousSiblingNode);
console.log(nextSiblingNode);
console.log(parentNode);
```

Таким образом, с помощью этих методов можно легко перемещаться по дереву DOM и получать доступ к различным узлам документа.



# Навигационные свойства

Навигационные свойства применяются ко всем узлам в документе, включая текстовые узлы, узлы-элементы и узлы-комментарии.

### Коллекция childNodes

```javascript
const childNodes = bodyElement.childNodes;
console.log(childNodes);
````

# Манипуляция элементами

Для работы с узлами-элементами используются специальные свойства.

# Коллекция children

```javascript
const bodyChildren = bodyElement.children;
console.log(bodyChildren);
```

# Первые и последние дочерние элементы

```javascript
const firstChild = bodyElement.firstElementChild;
const lastChild = bodyElement.lastElementChild;
console.log(firstChild);
console.log(lastChild);
```

# Соседние и родительские элементы

```javascript
const previousSibling = bodyElement.previousElementSibling;
const nextSibling = bodyElement.nextElementSibling;
const parentElement = bodyElement.parentElement;

console.log(previousSibling);
console.log(nextSibling);
console.log(parentElement);
```

# Поиск произвольных элементов

Для поиска элементов в документе используются методы `querySelector` и `querySelectorAll`.

# Примеры использования `querySelectorAll`

```javascript
// Поиск по классу
const elemsOne = document.querySelectorAll('.lesson__list');
console.log(elemsOne);

// Поиск по тегу
const elemsTwo = document.querySelectorAll('li');
console.log(elemsTwo);

// Смешанный селектор тега и класса
const elemsThree = document.querySelectorAll('li.lesson__item-list');
console.log(elemsThree);

// Тег первого уровня вложенности
const elemsFour = document.querySelectorAll('.lesson__list>li');
console.log(elemsFour);

// Несколько классов
const elemsFive = document.querySelectorAll('.lesson__list, .lesson__text');
console.log(elemsFive);

// Вложенные классы
const elemsSix = document.querySelectorAll('.lesson__list .lesson__text');
console.log(elemsSix);

// По ID
const elemsSeven = document.querySelectorAll('#listItem');
console.log(elemsSeven);

// По атрибуту
const elemsEight = document.querySelectorAll('[data-item]');
console.log(elemsEight);

// Атрибут со значением
const elemsNine = document.querySelectorAll('[data-item="85"]');
console.log(elemsNine);
```

# Работа с результатами поиска

```javascript
// Получение конкретного элемента коллекции
const elems = document.querySelectorAll('li');
console.log(elems[2]);

// Перебор элементов коллекции
for (const item of elems) {
    console.log(item);
}

elems.forEach(item => {
    console.log(item);
});
```

# Поиск внутри поддеревьев

```javascript
const subList = document.querySelectorAll('.lesson__sub-list');
const subItems = subList[0].querySelectorAll('li');
console.log(subItems);
```

# Неожиданные результаты поиска

```javascript
const subList = document.querySelectorAll('.lesson__sub-list');
const listItems = subList[0].querySelectorAll('.lesson__list .lesson__item-sub-list');
console.log(listItems);
```

Обратите внимание, что при поиске с использованием сложных селекторов, контекст поиска может влиять на результаты.

Таким образом, используя методы `children`, `firstElementChild`, `lastElementChild`, а также `previousElementSibling`, `nextElementSibling` и `parentElement`, вы можете эффективно перемещаться по дереву DOM и находить нужные элементы.




# Методы поиска элементов

Существуют разные методы для поиска элементов в DOM.

### Использование `querySelector`

Метод `querySelector` возвращает первый элемент, соответствующий заданному CSS-селектора.

```javascript
const lessonList = document.querySelector('.lesson__list');
console.log(lessonList);
````

# Метод `getElementById`

Если у элемента есть уникальный идентификатор (`id`), его можно найти с помощью метода `getElementById`.

```javascript
const elem = document.getElementById('listItem');
console.log(elem);
```

# Метод `getElementsByTagName`

Метод `getElementsByTagName` ищет элементы с указанным тегом и возвращает их коллекцию. Передача `"*"` вместо тега позволяет получить всех потомков.

```javascript
const elems = document.getElementsByTagName('li');
console.log(elems);
```

# Метод `getElementsByClassName`

Метод `getElementsByClassName` возвращает элементы, имеющие указанный CSS-класс.

```javascript
const elems = document.getElementsByClassName('lesson__item-list');
console.log(elems);
```

# Метод `getElementsByName`

Метод `getElementsByName` находит элементы с заданным атрибутом `name`. Этот метод используется редко.

```javascript
const elems = document.getElementsByName('list');
console.log(elems);
```

# Разница между живыми и статическими коллекциями

Некоторые методы возвращают живые коллекции, которые обновляются автоматически при изменении структуры DOM, тогда как другие возвращают статические коллекции, фиксированные на момент вызова.

```javascript
// Статическая коллекция
const listStatic = document.querySelectorAll('.lesson__item-list');

// Живая коллекция
const listLive = document.getElementsByClassName('lesson__item-list');

console.log(listStatic);
console.log(listLive);

// Добавляем новый элемент
const lessonList = document.querySelector('.lesson__list');
lessonList.insertAdjacentHTML(
    'beforeend',
    '<li class="lesson__item-list">Новый пункт</li>'
);
```

Эти методы помогают гибко искать и выбирать элементы в документе, учитывая особенности каждой задачи.

# Метод `closest`

Метод `elem.closest(css)` ищет ближайшего предка, который соответствует указанному CSS-селектору. Сам элемент также включается в поиск.

```javascript
const elem = document.querySelector('.lesson__item-sub-list');
const parentList = elem.closest('.lesson__list');
console.log(parentList);
````

Этот метод полезен для проверки существования определенного родителя или для изменения родителя конкретного элемента.

# Проверка `matches`

Метод `matches` проверяет, удовлетворяет ли элемент заданному CSS-селектора, и возвращает `true` или `false`.

```javascript
const elems = document.querySelectorAll('.lesson__item-list');
for (let elem of elems) {
    if (elem.matches('[class$="lesson__item-list_red"]')) {
        console.log('Красный');
    } else if (elem.matches('[class$="lesson__item-list_blue"]')) {
        console.log('Синий');
    }
}
```

# Применение свойств навигации

После получения объекта любым методом, можно использовать свойства навигации для перемещения по дереву DOM.

```javascript
const text = document.querySelector('.lesson__text');
const list = text.nextElementSibling;
console.log(list);
```

Эти методы помогают эффективно находить и проверять элементы в документе, а также перемещаться по структуре DOM.


# Изменение содержимого документа

## Свойство `innerHTML`

Свойство `innerHTML` позволяет получить или установить содержимое элемента вместе с HTML-разметкой.

```javascript
const textElement = document.querySelector('.lesson__text');

// Получение содержимого
const textElementContent = textElement.innerHTML;
console.log(textElementContent);

// Замена содержимого
textElement.innerHTML = `Живи, а работай в свободное время!`;

// Дополнение содержимого
textElement.innerHTML += `<p>${textElementContent}</p> <p>Живи, а работай в <span class="yellow">свободное</span> время!</p>`;

console.log(textElement.innerHTML);
````

# Свойство `outerHTML`

Свойство `outerHTML` позволяет получить или установить содержимое элемента вместе с самим элементом.

```javascript
const textElement = document.querySelector('.lesson__text');

// Получение содержимого
const textElementContent = textElement.outerHTML;
console.log(textElementContent);

// Замена содержимого
textElement.outerHTML = `<p>Живи, а работай в <span class="yellow">свободное</span> время!</p>`;

console.log(textElement.outerHTML);
```

# Свойство `textContent`

Свойство `textContent` позволяет получить или установить простой текстовый контент элемента, игнорируя HTML-теги.

```javascript
const textElement = document.querySelector('.lesson__text');

// Получение текста
const textElementContent = textElement.textContent;
console.log(textElementContent);

// Установка текста
textElement.textContent = `<p>Живи, а работай в <span class="yellow">свободное</span> время!</p>`;

console.log(textElement.textContent);
```

# Содержимое текстовых узлов и комментариев

Текстовые узлы и комментарии могут быть изменены с помощью свойства `data`.

```javascript
const textElement = document.querySelector('.lesson__text');
const getComment = textElement.nextSibling;

console.log(getComment);
console.log(getComment.data);

// Изменение содержимого комментария
getComment.data = 'Привет';
console.log(getComment.data);
```

# Создание новых элементов и узлов

Методы `createElement` и `createTextNode` позволяют создавать новые элементы и текстовые узлы соответственно.

```javascript
// Создание нового элемента
const newElement = document.createElement('div');
newElement.innerHTML = `Живи, а работай в <span class="yellow">свободное</span> время!`;
console.log(newElement);

// Создание текстового узла
const newText = document.createTextNode('Привет!');
console.log(newText);
```

Созданные таким образом объекты пока не являются частью документа и должны быть вставлены в дерево DOM вручную.


# Методы вставки

Существует несколько методов для вставки элементов в документ.

### Методы `before`, `after`, `prepend`, `append`

Эти методы позволяют вставлять элементы относительно указанного узла.

```javascript
const textElement = document.querySelector('.lesson__text');
const newElement = document.createElement('div');
newElement.innerHTML = `Живи, а работай в <span class="yellow">свободное</span> время!`;

// Вставляем новый элемент...
// ...перед объектом
textElement.before(newElement);
// ...после объекта
textElement.after(newElement);
// ...внутрь и в начало объекта
textElement.prepend(newElement);
// ...внутрь и в конец объекта
textElement.append(newElement);

// Вставка нескольких фрагментов сразу
textElement.append(newElement, "Привет!");

// Можно вставлять строку
textElement.append(`Живи, а работай в <span class="yellow">свободное</span> время!`);
````

# Метод `insertAdjacentHTML`

Метод `insertAdjacentHTML` позволяет вставлять HTML-контент относительно указанного узла.

```javascript
const textElement = document.querySelector('.lesson__text');
textElement.insertAdjacentHTML(
    'afterend',
    `<p>Живи, а работай в <span class="yellow">свободное</span> время!</p>`
);
```

# Методы `insertAdjacentText` и `insertAdjacentElement`

Также существуют методы `insertAdjacentText` и `insertAdjacentElement` для вставки текста и элементов соответственно.

```javascript
const textElement = document.querySelector('.lesson__text');
textElement.insertAdjacentText(
    'beforeend',
    `Живи, а работай в <span class="yellow">свободное</span> время!`
);

const newElement = document.createElement('div');
newElement.innerHTML = `Живи, а работай в <span class="yellow">свободное</span> время!`;
textElement.insertAdjacentElement(
    'beforeend',
    newElement
);
```

# Перенос элемента

Элементы можно переносить с одного места на другое, при этом они удаляются со старого места.

```javascript
const lessonBlock = document.querySelector('.lesson');
const title = document.querySelector('h3');
lessonBlock.append(title);
```

# Клонирование узлов `cloneNode`

Метод `cloneNode` создает копию узла. Если передать `true`, будет выполнено глубокое клонирование вместе с содержимым.

```javascript
const textElement = document.querySelector('.lesson__text');
const cloneTextElement = textElement.cloneNode(true);
const lessonBlock = document.querySelector('.lesson');
lessonBlock.append(cloneTextElement);
```

# Удаление узлов

Метод `remove` удаляет узел из документа.

```javascript
const textElement = document.querySelector('.lesson__text');
textElement.remove();
```

Эти методы позволяют гибко управлять структурой документа, добавлять, удалять и перемещать элементы.


# Управление классами

Классы являются важным инструментом для управления внешним видом элементов. В JavaScript существует два основных способа работы с классами: через свойства `className` и `classList`.

### Свойство `className`

Свойство `className` позволяет получить или установить имя класса элемента.

```javascript
const element = document.querySelector('.lesson__item-list_red');

// Получение имени класса
const elementClassNames = element.className;
console.log(elementClassNames);

// Перезапись имени класса
element.className = "red";
````

# Свойство `classList`

Свойство `classList` предоставляет набор методов для удобного управления классами.

```javascript
const element = document.querySelector('.lesson__item-list_red');

// Добавление класса
element.classList.add('active');

// Удаление класса
element.classList.remove('active');

// Переключение класса (добавляет, если его нет; удаляет, если есть)
element.classList.toggle('active');

// Проверка наличия класса
if (element.classList.contains('active')) {
    console.log(`У element есть класс active!`);
}

// Перебор всех классов
for (let className of element.classList) {
    console.log(className);
}
```

# Управление стилями

# Свойство `style`

Свойство `style` позволяет задать стили элемента напрямую.

```javascript
element.style.color = "red";   // Цвет текста
element.style.marginBottom = "30px";  // Отступ снизу
element.style.zIndex = "10";  // Индекс слоя

// Получение значения свойства
console.log(element.style.marginBottom);

// Сброс стиля
element.style.marginBottom = "";
```

# Полная перезапись стилей: `cssText`

Свойство `cssText` позволяет полностью переписать стили элемента.

```javascript
const element = document.querySelector('.lesson__item-list_red');

element.style.cssText = `
    margin-bottom: 30px;
    color: red;
`;
```

# Вычисленные стили: `getComputedStyle`

Функция `getComputedStyle` возвращает вычисленное значение стиля элемента.

```javascript
const elementStyle = getComputedStyle(element);
console.log(elementStyle.fontSize);

// Стиль псевдоэлемента
const elementBeforeStyle = getComputedStyle(element, "::before");
console.log(elementBeforeStyle.backgroundColor);


// Получаем точное значение
console.log(elementStyle.paddingLeft);

// Получаем не предсказуемую запись
console.log(elementStyle.padding); // В FF <empty string>
```


```javascript
// Получаем элемент
const element = document.querySelector('.lesson__item-list_red');

// Стиль элемента
const elementStyle = getComputedStyle(element);

//Только для чтения
elementStyle.paddingLeft = "50px";
```



# Лайфхаки

## Получение числовых значений из стилей

Иногда нужно извлечь числовое значение из стиля, но проблема заключается в том, что оно возвращается в виде строки с единицами измерения (например, `"10px"`). Чтобы преобразовать его в чистое число, можно воспользоваться функцией `parseInt`.

```javascript
// Получаем элемент
const element = document.querySelector('.lesson__item-list_red');

// Стиль элемента
const elementStyle = getComputedStyle(element);
console.log(elementStyle.paddingLeft);

// Преобразование в число
const paddingLeft = parseInt(elementStyle.paddingLeft);
console.log(paddingLeft);
````

# Установка стилей с учетом единиц измерения

При установке стилей важно помнить о необходимости указывать единицы измерения, такие как `px`, `em`, `%` и другие.

```javascript
// Устанавливаем отступ слева
element.style.marginLeft = "20px";
```

Использование таких лайфхаков помогает упростить работу с CSS-стилями в JavaScript.


# Атрибуты и свойства

У разных DOM-элементов могут быть разные свойства. Например, у тега `<a>` есть свойства, связанные со ссылками, а у тега `<input>` – свойства, связанные с полем ввода и т.д.

В HTML у тегов могут быть атрибуты. Когда браузер парсит HTML, чтобы создать DOM-объекты для тегов, он распознаёт стандартные атрибуты и создаёт DOM-свойства для них.

Каждый DOM-узел принадлежит соответствующему встроенному классу.

```javascript
const link = document.querySelector('.lesson__link');
const input = document.querySelector('.lesson__input');

console.log(link.href);
console.log(input.href);

console.log(input.value);
console.log(link.value);

// Получить список доступных свойств
console.dir(link);
````

# Произвольные атрибуты

Мы можем обращаться к любому атрибуту через методы доступа к атрибутам.

```javascript
// Получаем элемент
const lessonText = document.querySelector('.lesson__text');

// Проверяем наличие атрибута
lessonText.hasAttribute('name');

// Получаем значение атрибута
lessonText.getAttribute('name');

// Устанавливаем значение атрибута
lessonText.setAttribute('name', 'value');

// Удаляем атрибут
lessonText.removeAttribute('name');
```

Пример установки и проверки атрибута:

```javascript
// Устанавливаем значение атрибута
lessonText.setAttribute('some-attribute', 'some-value');

// Проверяем наличие атрибута
if (lessonText.hasAttribute('some-attribute')) {
    console.log('some-attribute существует!');
}
```

# Синхронизация между атрибутами и свойствами

Мы можем обратиться к тому или иному свойству через методы доступа к атрибутам. Когда стандартный атрибут изменяется, соответствующее свойство автоматически обновляется. Это работает и в обратную сторону (за некоторыми исключениями).

```javascript
// Получаем элемент
const input = document.querySelector('.lesson__input');

input.setAttribute('id', '123');
console.log(input.id);

input.id = "321";
console.log(input.getAttribute('id'));
```

НО:

```javascript
input.setAttribute('value', 'Привет!');
console.log(input.value);

input.value = "Как дела?";
console.log(input.getAttribute('value'));
```

# Заключение

Атрибуты и свойства тесно связаны друг с другом, и управление ими осуществляется через соответствующие методы. Однако, стоит учитывать исключения, где синхронизация между ними нарушается.



# Нестандартные атрибуты и dataset

Мы уже использовали произвольные атрибуты, но это может быть рискованным подходом. Все атрибуты, начинающиеся с префикса `data-`, зарезервированы для использования программистами. Они доступны через свойство `dataset`.

```javascript
// Получаем элемент
const lessonText = document.querySelector('.lesson__text');

// Получение data-атрибута
console.log(lessonText.dataset.size);

// Перезапись data-атрибута
lessonText.dataset.size = "5810";
console.log(lessonText.dataset.sizeValue);
````

# Полезные свойства

```javascript
const link = document.querySelector('.lesson__link');

// Получение тега элемента
console.log(link.tagName);

// Скрытие/показ элемента
link.hidden = true;
console.log(link.hidden);
```



# Домашка

- Задача 1: Изменить цвет текста
Задача: Измените цвет текста элемента с class="text" на красный.

- Задача 2: Добавление нового элемента
Задача: Создайте новый элемент `<h1>` с текстом "Заголовок" и добавьте его перед элементом с class="content".

- Задача 3: Удаление элемента
Задача: Удалите элемент с id="removeMe" из документа.

- Задача 4: Создание списка
Задача: Создайте список (ul) с тремя элементами (li), каждый из которых содержит числа от 1 до 3.
