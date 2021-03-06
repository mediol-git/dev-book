---
description: 'Можна все на світі описати, але хто то буде все читати?'
---

# Урок 02. Семантична розмітка сторінки. Валідація.

### Мета:

* навчити писати семантичну розмітку html сторінок;
* учні мають уміти аналізувати дизайн-макет та по ньому планувати розмітку;
* виховати відповідальне ставлення до семантики з перших кроків у фронтенді.

### І. Організація навчального процесу

Ставимо плюси в чаті, щоб привернути увагу учнів та спонукати до роботи.

### ІІ. АОЗ \(Актуалізація опорних знань\)

1. Які групи html тегів ви знаєте?
2. В чому різниця між рядковими та блочними тегами?
3. Чи можна перетворити рядковий тег на блочний і навпаки? Як це зробити?
4. Як має називатись файл головної сторінки сайту?
5. Як можна запустити свій код у браузері?
6. Як додати текст-рибу до розмітки?

_**Можна опитування провести у формі тесту**_

### ІІІ. Повідомлення теми, мети та завдань уроку

Важливо її чітко сформулювати, визначити завдання уроку й основні питання, які учні повинні засвоїти \(освітні завдання уроку\).

### IV. Мотивація

Тут можна показати слайд про те, скільки коштує на виході чистий семантичний код, на відміну від невалідного. Розповісти, що важливо одразу вчитися писати код правильно.

### V. Повідомлення нового матеріалу

#### Структура HTML документу

Давайте розберемо, з чого складається найпростіший html документ

```text
<!-- Оголошення формату/типу документу --> 
<!DOCTYPE html>   
<html>
<head>
    <!-- Визначаємо систему кодування символів --> 
    <meta charset="utf-8">
    
    <!-- Встановлюмо параметри відображення сторінки на мобільних пристроях -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Даємо заголовок сторінки --> 	 
    <title>Title</title> 
    
    <!-- Підключаємо зовнішню таблицю стилів --> 	 
    <link media="all" rel="stylesheet" href="css/main.css">
    
    <!-- Підключаємо скрипти -->
    <script src="js/main.js"></script>
</head> 

<body>
    <!-- Основна частина документу -->
    
    <header>"Шапка" сайту</header>
	
    <main>Основний контент</main>
    
    <footer>"Підвал" сторінки</footer>
    
</body>
</html>
```

`<html> ... </html>` - обов'язковий тег, що вміщує всю структуру сторінки

`<head> ... </head>` - призначений для збереження службової інформації для браузера та пошукових систем

`<body> ... </body>` - "тіло" сторінки, в якому зберігається весь контент сторінки

В середині шапки сайту часто розміщується навігаційне меню. Для його визначення використовується тег `<nav>`, в середині якого саме меню створюється за допомогою маркованого списку. Елементи списку виступають пунктами меню. Схоже меню часто зустрічається і в підвалі сайту \(у футері\).

```text
<header>
    <nav>
        <ul>
            <li>Пугкт меню 1</li>
            <li>Пугкт меню 2</li>
            <li>Пугкт меню 3</li>
            <li>Пугкт меню 4</li>
            <li>Пугкт меню 5</li>
        </ul>
    </nav>
</header>
```

В основному контенті, всередині тега `<main>` можуть бути різні смислові блоки, в залежності від завдань проекту. Наприклад, односторінкові сайти \(лендінги\) складаються із секцій, блоги наповнені статтями, в інтернет-магазинів часто присутні бокові колонки. Для всіх них в HTM5 існують окремі теги. Всі вони ведуть парні та блочні. 

#### Семантичні теги для групування контенту:

* `<section>` - створює секцію, яка передбачає наявність заголовка;
* `<aside>` - створює бокову колонку сайту \(часто називається - сайдбар\). Таких колонок може бути декілька на одній сторінці і розрізняються вони класами;
* `<article>` - створює статтю. В ній може бути присутня інформація про автора - `<author>`, дата публікації - `<date>` або `<datetime>`, заголовок та ін;

#### Заголовки.

В специфікації мови HTML5 існує шість рівнів заголовків - від 1\(найголовніший\) до шостого. Приклад написання заголовків різного рівня.

```text
<h1>Заголовок 1 рівня</h1>
<h2>Заголовок 2 рівня</h2>
<h3>Заголовок 3 рівня</h3>
<h4>Заголовок 4 рівня</h4>
<h5>Заголовок 5 рівня</h5>
<h6>Заголовок 6 рівня</h6>
```

{% hint style="info" %}
Важливо пам'ятати, що згідно із правилами семантичного коду на одній сторінці сайту заголовок першого рівня можна використовувати один раз.
{% endhint %}

Інші заголовки можна використовувати скільки завгодно разів, але варто дотримуватися їх ієрархії.

#### Взаємовідносини між тегами: батьківський, дочірній, сестринський, сусідній

![&#x421;&#x445;&#x435;&#x43C;&#x430; &#x432;&#x456;&#x434;&#x43D;&#x43E;&#x441;&#x438;&#x43D; &#x43C;&#x456;&#x436; &#x442;&#x435;&#x433;&#x430;&#x43C;&#x438;](.gitbook/assets/tad-ierarhy.jpg)

Варто вчителю разом із учнями розібрати представлену схему!

#### Коментарі

Коментар в HTML-коді задається так:

`<!-- будь-який текст чи код -->`

Текст всередині коментаря не відображається браузером на сторінці.

Коментарі зазвичай використовуються в наступних випадках: 

1. Для коментування коду. Завжди корисно залишити підказку.
2. Для тимчасового відключення коду. Видаляти код незручно, так як його треба буде відновлювати, а закоментувати і потім розкоментувати — найкраще рішення.

Коментарі можна використовувати в будь — якому місці сторінки, крім тега - всередині нього вони не працюють.

#### Стандарти верстки. Валідація.

Всі технології підпорядковуються певним стандартам та правилам. Це стосується й HTML.

**Валідна верстка** - це верстка, яка зроблена за всіма стандартами W3C \(www consortium\). Тобто верстку можна вважати валідною лише тоді, коли вона буде відповідати встановленим W3C стандартам.

#### Переваги валідної верстки

* Перша перевага - **кроссбраузерність**. Цим поняттям позначають правильне і однакове відображення верстки у всіх популярних браузерах. В першу чергу це: Opera, Chrome, Mozilla FireFox, Safari, а так само Internet Explorer \(куди ж без нього\)\) \). Завдяки тому, що браузери постійно вносять коригування в свої продукти щодо вимог Всесвітнього веб консорціуму. Звідси випливає що валідність стає синонімом кросбраузерності.
* Другий плюс валідної верстки - пошукові системи. Вони, так само як і браузери, відстежують стандарти і використовуючи їх вносять коригування в пошукову видачу. Варто відразу помітити, що бувають і винятки у ПС, але в основній масі валідна верстка все-таки грає роль в ранжируванні \(незважаючи на те, що у самих пошуковиків в районі сотні помилок у валідації\). 

#### Як перевірити валідність \(правильність\) верстки?

Все досить просто! Щоб з'ясувати наскільки правильна ваша верстка досить зайти на сайт validator.w3.org і там перевірити хоч за посиланням на сайт, хоч завантаживши файл сторінки і навіть скопіювавши код у вікно на сайті.

{% hint style="warning" %}
Валідація HTML - [https://validator.w3.org/](https://validator.w3.org/)
{% endhint %}

### VI. Узагальнення та систематизація знань

* Яка базова структура html сторінки?
* За що відповідає елемент `<head>`?
* Як можна розрізняти бокові колонки, якщо їх декілька на одній сторінці?
* На прикладі коду, що на екрані, назвіть батьківські, дочірні та сестринські елементи.
* Коли саме варто використовувати коментарі?
* Поясніть поняття кросбраузерності.

### VII. Домашнє завдання

#### Завдання 1

Створити 2 маркованих списку:

* Перший повинен містити `li`, всередині яких будуть імена `рядкових` тегів вивчених в модулі.
* Другий повинен містити `li`, всередині яких будуть імена `блокових` тегів вивчених в модулі.
* Використовуйте [цей ресурс](http://htmlreference.io/) для пошуку і додаткової довідки за тегами.

#### Завдання 2

Зверстати блок статті складається з зображення, заголовка, абзацу та посилання. Текст і зображення візьміть будь-яку.

#### Завдання 3

Зверстати нумерований список. У кожному елементі списку є заголовок і абзац тексту. Для заповнення використовуйте текс-рибу.

![](.gitbook/assets/ol_list.png)

#### Завдання 4

Зверстати маркований список, щоб кожен елемент був посиланням на соцмережу. При кліці на посилання, вона відкривається в новій вкладці браузера.

![](.gitbook/assets/links.png)

