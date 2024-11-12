
## Проверка домашки

- [повторение лекции](lecture8)
- - Доделать hero section на [макете](https://www.figma.com/design/sJwabNIQ83JF9XIGfYCOl4/Simple?node-id=0-1&node-type=canvas&t=75tl415eGMcEFtbY-0) , а именно: сделать адаптивную картинку (справа) с помощью background'а
+ сделать 2 секцию макета, там где много картинок, с адаптивом
### Архив с готовым [макетом](https://www.figma.com/design/sJwabNIQ83JF9XIGfYCOl4/Simple?node-id=0-1&node-type=canvas&t=75tl415eGMcEFtbY-0)

- Архив с проектом находиться в телеграмм канале frontend группы
архив - https://t.me/c/2339092402/213



## GridCSS
## Основные термины

- **Grid Container**: Элемент, к которому применяется `display: grid;`.
- **Grid Item**: Элемент внутри grid-контейнера.
- **Grid Line**: Линии, которые разделяют строки и столбцы.

## Основные свойства контейнера

### 1. `display: grid;`

Активирует grid-контейнер.

### 2. `grid-template-columns` / `grid-template-rows`

Определяет количество и размеры столбцов и строк.

```css
.grid-container {  
	grid-template-columns: 100px 200px 1fr; 
	/* 1 колонка 100px, 2 колонка 200px, 3-... */
	
	grid-template-rows: 50px 100px; 
	/* первый ряд в высоту 50px, второй 100px */
}
```

```css
.grid-container {  
	grid-template-columns: repeat(5, 100px) 
	/* 5 колонок по 100px */
}
```

```css
.grid-container {  
	grid-template-columns: repeat(5, 1fr) 
	/* 5 колонок по 1fr */
}
```

- `1fr` означает "одна доля" свободного пространства.
- Если несколько столбцов или строк заданы в `fr`, доступное пространство делится между ними пропорционально.

### 3. `grid-column-gap` / `grid-row-gap`

Задает расстояние между столбцами/строками (устарело, лучше использовать `gap`).


```css
.grid-container {   
	grid-column-gap: 20px; /* Отступ между колонок в 20px */
	grid-row-gap: 10px; /* Отступ между рядами в 10px */
}
```

### 4. `gap`

Современная версия, задает как вертикальные, так и горизонтальные расстояния между элементами.


```css
.grid-container {   
	gap: 20px; /* Отступ между колонок и рядов в 20px */
}
```

### 5. `grid-template-areas`

Задает именованные области сетки.


```css
.grid-container {
	grid-template-areas:     
		"header header header"     
		"sidebar content content"    
		"footer footer footer"; 
}
```

Использование:

```css
.grid-item {
	grid-area: header; 
}
```

## Основные свойства элементов

### 6. `grid-column` / `grid-row`

Определяет, как элемент будет располагаться на сетке (на каких строках и столбцах).


```css
.grid-item {
	grid-column: 1 / 3; /* От первого до третьего столбца */   
	grid-row: 2 / 4; /* От второй до четвертой строки */ 
}
```

### 7. `grid-area`

Задает местоположение элемента через сокращение для `grid-row` и `grid-column`, либо ссылку на область из `grid-template-areas`.

```css
.grid-item { 
	grid-area: 1 / 2 / 3 / 4; /* start-row / start-column / end-row / end-column */ 
}
```

## Выравнивание в сетке

### 8. `justify-items`

Выравнивает элементы по горизонтали в пределах ячеек.


```css
.grid-container {
	justify-items: start; /* start, end, center, stretch */ 
}
```


### 9. `align-items`

Выравнивает элементы по вертикали в пределах ячеек.


```css
.grid-container {  
	align-items: center; /* start, end, center, stretch */ 
}
```

### 10. `justify-content`


Выравнивает сетку по горизонтали относительно контейнера.


```css
.grid-container {  
	justify-content: space-between;
	/* start, end, center, space-between, space-around */ 
}
```

### 11. `align-content`

Выравнивает сетку по вертикали относительно контейнера.

```css
.grid-container {   
	align-content: center; /* start, end, center, space-between, space-around */ 
}
```

## Автоматическое размещение

### 12. `grid-auto-rows` / `grid-auto-columns`

Задает размеры строк или столбцов, которые создаются автоматически.


```css
.grid-container { 
	grid-auto-rows: 100px;
	grid-auto-columns: minmax(100px, auto); 
}
```

### 13. `grid-auto-flow`

Определяет порядок добавления элементов (по строкам или столбцам).
```css 
.grid-container {   
	grid-auto-flow: row; /* row, column, dense */
}
```

## Примеры

### Пример 1: Простой макет

```css
.container {   
	display: grid;  
	grid-template-columns: 1fr 2fr;   
	grid-template-rows: auto;  
	gap: 10px; 
} 
.item1 {  
	grid-column: 1 / 3;  /* Занимать с первой по шестую колонку */
} 
.item2 { 
	grid-column: 1;
} 
.item3 {  
	grid-column: 2;
}
```

### Пример 2: Использование `grid-template-areas`

```css
.container {  
	display: grid;  
	grid-template-areas: 
			"header header"    
			"sidebar content"
			"footer footer";  
	grid-gap: 10px;
} 
.header {   
	grid-area: header; 
} 
.sidebar {   
	grid-area: sidebar;
} 
.content {  
	grid-area: content;
} 
.footer {  
	grid-area: footer;
}
```

## Полезные ссылки

- [CSS Grid Guide by MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)

## Домашка

- Отточить свои знания по [GridCSS](gridcss.md)
- Применить на практике -> разработать сайт в своём стиле на котором:
	- Будет адаптированный **header**
	- Будет секция с товарами (`grid` сетка), также адаптированная для мобилки
	- Будет адаптированный **footer**

