**В наше время все смотрят на красоту и они готовы на всё, чтобы добиться этой красоты и поэтому наш сайт должен выглядеть очень красиво, для этого придумали `CSS магию` - transition или же animation **

### Свойства transitioncss

#### `transition-property`
**Описание:** Определяет свойство CSS, которое будет использовать эффект перехода. 

**Пример:**
```css
/* Переход для всех свойств */
transition-property: all;

/* Переход только для цвета фона и высоты */
transition-property: background-color, height;
```


# `transition-duration`

**Описание:** Устанавливает длительность эффекта перехода в секундах или миллисекундах.

**Пример:**

```css
/* Длительность перехода 2 секунды */
transition-duration: 2s;

/* Длительность перехода 0.5 секунды */
transition-duration: 0.5s;
```

# `transition-timing-function`

**Описание:** Определяет функцию кривой скорости анимации. По умолчанию используется функция "ease", которая обеспечивает плавное начало и конец анимации.

**Примеры:**

```css
/* Плавный переход (по умолчанию) */
transition-timing-function: ease;

/* Линейная анимация */
transition-timing-function: linear;

/* Быстрый старт и замедление к концу */
transition-timing-function: ease-in-out;
```

# `transition-delay`

**Описание:** Задает задержку начала эффекта перехода в секундах или миллисекундах после изменения свойства.

**Пример:**

```css
/* Задержка начала перехода на 1 секунду */
transition-delay: 1s;

/* Задержка начала перехода на 0.3 секунды */
transition-delay: 0.3s;
```

# Полный синтаксис transitioncss

Для указания всех параметров transitioncss используется следующий синтаксис:

```css
transition: property duration timing-function delay;
```

**Пример:**

```css
/* Пример полной настройки transitioncss */
transition: background-color 1s linear 0.5s;
```

