##  TransformCSS

# translate

```css
transform: translateX(-10px); /* Перемещение по оси X */
transform: translateY(20px); /* Перемещение по оси Y */
transform: translateZ(30px); /* Перемещение по оси Z (для 3D объектов) */
```

Примеры перемещения элемента вдоль одной из осей.

# skew

```css
transform: skewX(20deg); /* Наклон по оси X */
transform: skewY(10deg); /* Наклон по оси Y */
```

Примеры наклона элемента вдоль одной из осей.

# matrix

```css
transform: matrix(a, b, c, d, e, f); /* Матрица 2x3 */
```

Матричное преобразование, где `a`, `b`, `c`, `d`, `e`, `f` - коэффициенты матрицы.

# perspective

```css
transform: perspective(100px); /* Создает перспективу для 3D объектов */
```

Создает перспективу для 3D объектов.

# rotate3d

```css
transform: rotate3d(x, y, z, angle); /* Вращение вокруг осей x, y, z */
```

Вращение объекта вокруг трех осей.

# rotateX/Y/Z

```css
transform: rotateX(angle); /* Вращение вокруг оси X */
transform: rotateY(angle); /* Вращение вокруг оси Y */
transform: rotateZ(angle); /* Вращение вокруг оси Z */
```

Вращение объекта вокруг конкретной оси.

# scale

```css
transform: scale(sx); /* Изменение размера по обеим осям */
transform: scale(sx, sy); /* Изменение размера по отдельным осям */
```

Изменение размеров элемента.

# scale3d

```css
transform: scale3d(sx, sy, sz); /* Изменение размера по трем осям */
```

Трехмерное изменение размера.

# scaleX/Y/Z

```css
transform: scaleX(sx); /* Изменение размера только по оси X */
transform: scaleY(sy); /* Изменение размера только по оси Y */
transform: scaleZ(sz); /* Изменение размера только по оси Z */
```

Изменение размера только по одной из осей.

# transform-origin

```css
transform-origin: top left; /* Начальная точка преобразований */
transform-origin: center; /* Центральная точка преобразований */
```

Установка начальной точки для всех преобразований.

# transform-style

```css
transform-style: flat; /* Принудительно плоское отображение без 3D эффектов */
transform-style: preserve-3d; /* Сохраняет 3D структуру элементов при трансформациях */
```

Управление способом обработки 3D преобразований.

# backface-visibility

```css
backface-visibility: visible; /* Видимость обратной стороны элемента */
backface-visibility: hidden; /* Скрытие обратной стороны элемента */
```

Управление видимостью обратной стороны элемента при вращении.

### perspective-origin

```css
perspective-origin: top left; /* Точка начала перспективы */
perspective-origin: center; /* Центральная точка перспективы */
```

Установка точки начала перспективы для 3D объектов

#### transform (универсальное свойство)
```css
transform: rotate(45deg) scale(0.5); /* Пример */
```
Пример комбинации двух свойств `rotate` и `scale`.