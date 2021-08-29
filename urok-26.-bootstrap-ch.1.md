# Урок 26. Bootstrap \(ч.1\)

### Мета:

* познайомитись із новими технологіями розробки сайтів 
* розвивати навички використання сучасного фреймворка у реальних проектах
* виховувати повагу до чужих розробок

### І. АОЗ

1. Як зазвичай називають кнопку для мобільного меню?
2. Як можна відстежити натискання "бургер" кнопки?
3. У яких випадках варто основне меню перетворювати на мобільне?

### ІІ. Оголошення теми. мети та завдань уроку

Сьогодні ми познайомимось із новими технологіями розробки сайтів. Ми дізнаємося про фреймворки, а зокрема попрацюємо із Boottrap.

### ІІІ. Вивчення нового матеріалу

Фреймворк - це каркас або заготовка для розробника. Тобто, це потужний набір бібліотек і готових інструментів, який дозволяє нам розробляти різноманітне ПЗ будь-якої складності, створювати веб-додатки і т.д. Все це дає змогу витрачати менше зусиль та часу.

Плюси фреймворків:

* прискорення та зручність розробки
* кросбраузерність
* скорочення затрат на створення проекту
* можливість створювати коректний HTML макет навіть не дуже досвідченому спеціалісту
* оптимізація робочого часу

Простіше кажучи, замість того, щоб писати сотні рядків коду достатньо викликати декілька команд або методів і робота готова.

Але, в нашому світі немає нічого ідеального. Саме тому, у фреймворків є **недоліки**:

* прив'язаність до стилів CSS бібліотеки
* надлишковий код
* складність опанування

Як ви здогадались, фреймворків існує достатня кількість. Та ми з вами вивчимо один із найпопулярніших, який використовується розробниками у всьому світі. Це - **Bootstrap**.

Він складається за:

* розмітки
* класів для стилізації тексту, зображень. блоків, таблиць а ін
* компонентів призначених для створення кнопок, форм, меню, слайдерів, списків і т.д.
* класів для вирішення допоміжних задач типу: вирівнювання тексту, приховування елементів, колір, фон, відступи та ін.

#### Установка

**Швидкий спосіб \(Bootstrap CDN\)**

Достатньо вставити наступний код в розділ `<head>`

```text
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
```

А для активації плагінів, требв розмістити наступний код в кінці сторінки перед закриваючим тегом `</body>`

```text
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js" integrity="sha384-IQsoLXl5PILFhosVNubq5LC7Qb9DXgDA9i+tQ8Zj3iwWAwPtgFTxbJ8NT4GN1R8p" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.min.js" integrity="sha384-cVKIPhGWiC2Al4u+LWgxfKTRIcfu0JTxR+EQDz/bgldoEyl4H0zUF0QKbrJ0EcQF" crossorigin="anonymous"></script>
```

Базовий шаблон сторінки буде виглядати таким чином:

```text
<!doctype html>
<html lang="ru">
  <head>
    <!-- Обязательные метатеги -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

    <title>Привет мир!</title>
  </head>
  <body>
    <h1>Привет мир!</h1>

    <!-- Дополнительный JavaScript; выберите один из двух! -->

    <!-- Вариант 1: Bootstrap в связке с Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>

    <!-- Вариант 2: Bootstrap JS отдельно от Popper
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js" integrity="sha384-IQsoLXl5PILFhosVNubq5LC7Qb9DXgDA9i+tQ8Zj3iwWAwPtgFTxbJ8NT4GN1R8p" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.min.js" integrity="sha384-cVKIPhGWiC2Al4u+LWgxfKTRIcfu0JTxR+EQDz/bgldoEyl4H0zUF0QKbrJ0EcQF" crossorigin="anonymous"></script>
    -->
  </body>
</html>
```

**Другий варіант встановлення** - завантажити його [тут](https://getbootstrap.com/docs/4.4/getting-started/download/)

#### Розмітка

В Bootstrap використовується система "12 колонок". Сітка базується на CSS Flexbox та медіа-запитах.

![](.gitbook/assets/img-17-tb02.png)

Bootstrap містить в собі responsive **mobile first сітку.** Вона, в свою чергу, містить заздалегідь визначені класи для легкості створення семантичної розмітки.

На схемі показано основні контрольні точки, які використовує Bootstrap

![](.gitbook/assets/bootstrap-4-five-grid-tiers.jpg)

| Ширина viewport браузера | Контрольна точка \(назва пристрою\) |
| :--- | :--- |
| &gt;=0 | без позначення\(xs\) |
| &gt;=576px | "sm" |
| &gt;=768px | "md" |
| &gt;=992px | "lg" |
| &gt;=1200px | "xl" |

Сітка Bootstrap 4 - це основна частина фреймворку. Вона складається з:

* контейнерів \(елементів з класом `container` та `container-fluid`\)
* рядків \(елементів з класом `row`\)
* адаптивних блоків \(елементів із декількома класами `col`, або що починаються на `col`\)

Усе це звичайні HTML елементи, до яких просто додані певні класи. А вже до класів написані потрібні стилі.

### IV. Засвоєння нових знань на практиці

### V. Узагальнення вивченого матеріалу

### VI. Домашнє завдання

