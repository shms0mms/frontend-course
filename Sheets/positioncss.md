
## Position CSS - позиционированние элементов

**Позиционирование - это термин, означающий возможность с помощью CSS изменить стандартную логику потока для элемента.**

**То есть, мы можем, подвинуть элемент куда-нибудь, можем разместить один элемент сверху над остальными, можем вообще зафиксировать элемент в какой-то части экрана, чтоб он оставался там, даже если страница будет скроллится.**


## Пример 1 
**Свойство `position: static;`**

- Добавьте в HTML разметку данный код 

```html
<div class="blocks blocks-1">
	<div class="block block-1"></div>
	<div class="block block-2"></div>
	<div class="block block-3"></div>
</div>
```

- Создайте файл style.css (не забудьте подключить к HTML) И скопируйте туда эти стили

```css

/* Добавление переменных цветов */
:root {
   --accent: #5f5975;
   --secondary: #32b5a4;
   --yellow: #ebe691;
}


/* Сам блок */

.block {
   height: 80px;
   width: 100%;
   display: flex;
   justify-content: center;
   align-items: center;
   color: white;
   font-size: 32px;
   font-weight: 800;
}

/* Цвет блока */

.block-1 {
   background-color: var(--yellow); /* Подключение переменной цветов */
}

.block-2 {
   background-color: var(--accent); /* Подключение переменной цветов */
}

.block-3 {
   background-color: var(--secondary); /* Подключение переменной цветов */
}

/* У каждого элемента по умолчанию стоит данное свойство с данным значением */
.blocks-1 {
   position: static;
}
.blocks-1 .block {
   position: static;
}

```

**После запустите проект и вы увидите как на сайте появились блоки 1,2,3 и каждый со своим цветом




## Пример 2
**Свойство `position: relative; + top + left`**

- Добавьте в HTML разметку данный код 

```html
<div class="blocks blocks-2">
	<div class="block block-1"></div>
	<div class="block block-2"></div>
	<div class="block block-3"></div>
</div>
```

- Создайте файл style.css (не забудьте подключить к HTML) И скопируйте туда эти стили

```css

/* Добавление переменных цветов */
:root {
   --accent: #5f5975;
   --secondary: #32b5a4;
   --yellow: #ebe691;
}


/* Сам блок */

.block {
   height: 80px;
   width: 100%;
   display: flex;
   justify-content: center;
   align-items: center;
   color: white;
   font-size: 32px;
   font-weight: 800;
}

/* Цвет блока */

.block-1 {
   background-color: var(--yellow); /* Подключение переменной цветов */
}

.block-2 {
   background-color: var(--accent); /* Подключение переменной цветов */
}

.block-3 {
   background-color: var(--secondary); /* Подключение переменной цветов */
}

/* Применяя значение relative мы можем добавить свойства top, left, c помощью которых можем позиционировать элемент */
.blocks-2 .block-2 {
   position: relative;
   top: 100px;
   left: 50px;
   bottom: 0px; /* Дополнительные свойства bottom */
   right: 0px; /* Дополнительные свойства right */
}

```

**После запустите проект и вы увидите как на сайте появились блоки 1,2,3 и каждый со своим цветом и блок-2 будет с отступом сверху на 100px и слева на 50px




## Пример 3
**Свойство `(position: absolute; + top + left) + position: relative; у родителя`**

- Добавьте в HTML разметку данный код 

```html
<div class="blocks blocks-3">
	<div class="block block-1"></div>
	<div class="block block-2"></div>
	<div class="block block-3"></div>
</div>
```

- Создайте файл style.css (не забудьте подключить к HTML) И скопируйте туда эти стили

```css
/* Добавление переменных цветов */
:root {
   --accent: #5f5975;
   --secondary: #32b5a4;
   --yellow: #ebe691;
}


/* Сам блок */

.block {
   height: 80px;
   width: 100%;
   display: flex;
   justify-content: center;
   align-items: center;
   color: white;
   font-size: 32px;
   font-weight: 800;
}

/* Цвет блока */

.block-1 {
   background-color: var(--yellow); /* Подключение переменной цветов */
}

.block-2 {
   background-color: var(--accent); /* Подключение переменной цветов */
}

.block-3 {
   background-color: var(--secondary); /* Подключение переменной цветов */
}

/* Применяя значение relative мы можем добавить свойства top, left, c помощью которых можем позиционировать элемент */
.blocks-3 {
	position: relative;
}

/* Позиционированние абсолютно */
/* Чтобы позиционировать элемент относительно родителя, нужно родителю (или же blocks-3) задать position: relative; если этого не сделать, то block-2 будет позиционироваться относительно тега body или же простым языком, относительно браузера */
.blocks-3 .block-2 {
   position: absolute;
   top: 100px;
   left: 50px;
}

/* Если мы посмотрим в браузере, то наш block-2 накроет элемент block-3 и чтобы block-3 был наложен поверх block-2, нам нужно block-3 задать z-index больше чем у block-2 (по дефолту у всех элементов z-index: 0) */
.blocks-3 .block-3 {
   position: absolute;
   z-index: 2;
}


```

**После запустите проект и вы увидите как на сайте появились блоки 1,2,3 и каждый со своим цветом и блок-2 будет позиционироваться относительно blocks-3 (так задан position: relative;), так вот, блок-2 отступит сверху на 100px от верха родителя и 50px слева от края родителя


## Пример 4
**Свойство `position: fixed; + bottom + left`**

- Добавьте в HTML разметку данный код 

```html
<div class="blocks blocks-4">
	<div class="block block-1"></div>
	<div class="block block-2"></div>
	<div class="block block-3"></div>
</div>
```

- Создайте файл style.css (не забудьте подключить к HTML) И скопируйте туда эти стили

```css

/* Добавление переменных цветов */
:root {
   --accent: #5f5975;
   --secondary: #32b5a4;
   --yellow: #ebe691;
}


/* Сам блок */

.block {
   height: 80px;
   width: 100%;
   display: flex;
   justify-content: center;
   align-items: center;
   color: white;
   font-size: 32px;
   font-weight: 800;
}

/* Цвет блока */

.block-1 {
   background-color: var(--yellow); /* Подключение переменной цветов */
}

.block-2 {
   background-color: var(--accent); /* Подключение переменной цветов */
}

.block-3 {
   background-color: var(--secondary); /* Подключение переменной цветов */
}

/* Позиционированние фиксированно */
/* Чтобы позиционировать элемент относительно окна браузера и чтобы он катался вместе с нами (пока мы скроллим сайт) то нужно задать свойство position: fixed; */


/* В данном примере мы указали block-2 position: fixed; bottom: 0; left: 0; тем самым наш элемент стал позиционироваться относительно окна браузера, и если мы запустим наш сайт, мы увидим, как наш block-2 находится приклеенным внизу сайта */
.blocks-3 .block-2 {
   position: fixed;
   bottom: 0px;
   left: 0px;
}

```

**После запустите проект и вы увидите как на сайте появились блоки 1,2,3 и каждый со своим цветом и блок-2 находится приклеенным внизу сайта и скроллится вместе с сайтом


## Пример 5
**Свойство `position: sticky;`**

- Добавьте в HTML разметку данный код 

```html
<div class="blocks blocks-5">
	<div class="block block-1"></div>
	<div class="block block-2"></div>
	<div class="block block-3"></div>
</div>
```

- Создайте файл style.css (не забудьте подключить к HTML) И скопируйте туда эти стили

```css

/* Добавление переменных цветов */
:root {
   --accent: #5f5975;
   --secondary: #32b5a4;
   --yellow: #ebe691;
}


/* Сам блок */

.block {
   height: 80px;
   width: 100%;
   display: flex;
   justify-content: center;
   align-items: center;
   color: white;
   font-size: 32px;
   font-weight: 800;
}

/* Цвет блока */

.block-1 {
   background-color: var(--yellow); /* Подключение переменной цветов */
}

.block-2 {
   background-color: var(--accent); /* Подключение переменной цветов */
}

.block-3 {
   background-color: var(--secondary); /* Подключение переменной цветов */
}

/* Чтобы позиционировать элемент так, чтобы он прилип к нам, когда мы до него доскроллим, то нужно задать следующее свойство */

/* В данном примере мы указали block-2 position: sticky; */
.blocks-3 .block-2 {
   position: sticky;
}

```

**После запустите проект и вы увидите как на сайте появились блоки 1,2,3 и каждый со своим цветом и блок-2 находится сначала находится среди наших блоков на своём месте, а если мы прокрутим чуть сайт, и захватим область данного блока, то он приклеится и будет скроллиться вместе с нами как `position: fixed;`