

### Теория

#### Что происходит при открытии сайта

1. **Запрос от браузера**: Браузер отправляет запрос на сервер, где хранятся файлы сайта.
2. **Обработка запроса сервером**: Сервер получает запрос, находит запрашиваемый файл и отправляет его обратно.
3. **Получение ответа браузером**: Браузер получает файлы и отображает веб-страницу на экране.

Эти файлы могут включать HTML-документы, изображения, аудио, видео и другие типы файлов.

#### За что отвечают HTML, CSS и JS

- **HTML**: Язык гипертекстовой разметки текста. Определяет структуру и содержание веб-страницы.
- **CSS**: Язык стилей. Определяет внешний вид и оформление веб-страницы.
- **JS**: Язык программирования, встроенный в веб-браузеры. Отвечает за интерактивность и логику веб-страницы.

#### Установка VS Code

- **Мини настройка**: Установите расширения EMMET и PRETTIER для удобства разработки.

### Практика
### Как создать папку и файл `index.html`

1. Создайте папку:
    
    - Откройте файловый менеджер (например, Проводник Windows или Finder на Mac).
    - Перейдите в место, где хотите создать папку.
    - Создайте новую папку (например, `my_website`).
    
1. Создайте файл `index.html`:
    
    - Внутри папки `my_website` создайте новый файл.
    - Назовите его `index.html`.
    
1. Напишите код в `index.html`:
    
    - Откройте `index.html` в вашем текстовом редакторе (например, VS Code).
    - Вставьте в файл HTML-код, представленный выше.

Теперь вы можете открыть файл `index.html` в вашем браузере, чтобы увидеть созданную веб-страницу.

#### Примеры кода HTML


1. **Основы HTML**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Пример страницы</title>
</head>
<body>
    <h1>Заголовок первого уровня</h1>
    <h2>Заголовок второго уровня</h2>
    <p>Это абзац текста. <a href="Путь к другой странице html">Это ссылка</a></p>
    <div>
        <img src="image.jpg" alt="Пример изображения">
    </div>
    <ul>
        <li>Первый элемент списка</li>
        <li>Второй элемент списка</li>
    </ul>
    <ol>
        <li>Первый элемент нумерованного списка</li>
        <li>Второй элемент нумерованного списка</li>
    </ol>
    <span>Это текст в элементе span.</span>
    <video controls src="video.mp4">
</body>
</html>
```





1.  Строчные и блочные теги
    
    - Строчные теги: `<a>`, `<span>`, `<img>`. Не занимают всю ширину родительского элемента.
    - Блочные теги: `<div>`, `<p>`, `<h1>`. Занимают всю ширину родительского элемента.
    
2. Атрибуты
    
    - class: Используется для присвоения стилей через CSS.
    - value: Используется для задания значения в элементах формы.





Домашняя работа 
  - Если нужно попрактиковаться, то можно создать простенький сайт в котором будет три страницы (для перемещения по ним есть тег "a"):
		- Главная
			- На главной можете сделать что угодно
		- Новости сайта
			- Простая страница на которой будет заголовок, разные новости в виде картинок, и какие-нибудь статьи в виде тега "p" 
		- Страница контактов 
			- там можно указать какой-нибудь Номер телефона, почту, и так далее. Также можно поставить перед номером телефона и почтой иконку какую-нибудь с помощью тега "img" (иконку найти в интернете)