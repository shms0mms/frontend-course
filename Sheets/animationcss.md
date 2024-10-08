
**В наше время все смотрят на красоту и они готовы на всё, чтобы добиться этой красоты и поэтому наш сайт должен выглядеть очень красиво, для этого придумали `CSS магию` - animation или же transition **

### Свойства анимации в CSS

#### animation-name
**Описание:** Указывает имя правила `@keyframes`, которое будет использоваться для анимации.
```css
animation-name: fadeInOut; /* Использует ключевые кадры, определенные правилом `@keyframes fadeInOut` */
````

# animation-duration

**Описание:** Устанавливает продолжительность анимации.

```css
animation-duration: 4s; /* Анимация длится 4 секунды */
```

# animation-timing-function

**Описание:** Определяет, как прогрессирует анимация со временем (функция смягчения).
**Значения:** `linear` (по умолчанию), `ease`, `ease-in`, `ease-out`, `ease-in-out`, `step-start`, `step-end`, `cubic-bezier(n, n, n, n)`.

```css
animation-timing-function: ease-in-out; /* Плавное затухание и начало анимации */
animation-timing-function: cubic-bezier(.2,.8,1,1); /* Пользовательская кривая смягчения */
```

# animation-delay

**Описание:** Откладывает начало анимации на определенный период времени.

```css
animation-delay: 2s; /* Начинает анимацию через 2 секунды */
```

# animation-iteration-count

**Описание:** Определяет, сколько раз должна повторяться анимация.

```css
animation-iteration-count: infinite; /* Бесконечно повторяет анимацию */
animation-iteration-count: 3; /* Повторяет анимацию три раза */
```

# animation-direction

**Описание:** Управляет направлением воспроизведения анимации.
**Значения:** `normal` (по умолчанию), `alternate`, `reverse`, `alternate-reverse`.

```css
animation-direction: alternate; /* Воспроизводит анимацию в обратном направлении на нечетных итерациях */
animation-direction: reverse; /* Воспроизводит анимацию в обратном порядке от начала к концу */
```

# animation-fill-mode

**Описание:** Определяет, что происходит с анимируемыми свойствами перед началом и после завершения анимации.
**Значения:** `none` (по умолчанию), `forwards`, `backwards`, `both`.

```css
animation-fill-mode: forwards; /* Сохраняет анимированные свойства после окончания анимации */
animation-fill-mode: both; /* Устанавливает начальные значения перед началом анимации и сохраняет конечные значения после ее завершения */
```

# animation-play-state

**Описание:** Позволяет приостановить и возобновить анимацию.

```css
animation-play-state: paused; /* Приостанавливает анимацию */
animation-play-state: running; /* Возобновляет анимацию, если она была ранее приостановлена */
```

# animation

**Описание:** Объединяет все отдельные свойства анимации в одну декларацию.

```css
animation: fadeInOut 4s ease-in-out 2s infinite alternate both;
/* Использует анимацию 'fadeInOut', которая длится 4 секунды, плавно начинается и заканчивается, задерживается на 2 секунды, бесконечно повторяется, меняет направление на нечетных итерациях, и сохраняет значения после завершения анимации */
```
