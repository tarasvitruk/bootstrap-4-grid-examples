# Bootstrap 4. Сетка. Подробное руководство
<h2>1. Основные параметры сетки по-умолчанию</h2>
<p>По-умолчанию сетка Bootstrap 4 очень похожа на сетку третьей версии, однако появились некоторые важные отличия.</p>
<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/1-1-grid-options.jpg"/>
<p>Из таблицы основных опций мы можем заметить явные отличия от сетки третьей версии. Теперь отсутствует префикс класса «.col-xs-», отвечающий за самые маленькие разрешения, вместо него указывается упрощенный префикс «.col-». Можно ошибочно подумать, что префикс «.col-» отвечает за минимальные разрешения мобильных устройств, однако это не совсем так. Помимо всего прочего, префикс «.col-» - это одно из важнейших новшеств Bootstrap 4. Это класс, который отвечает за автоматическую разметку колонок на любом разрешении. Но об этом позже.</p>
<p>За малые разрешения (small) отвечает префикс «.col-sm-» с медиа-запросом от 576 пикс. Ширина контейнера составляет 540 пикс. Средние разрешения отрабатываются от 768 пикс. Ширина контейнера - 720 пикс. Большие разрешения работают с разрешения устройств от 992 пикс. Ширина контейнера - 960 пикс. И самые большие - от 1200 пикс. Ширина контейнера фиксируется на значении 1140 пикс.</p>
<p>Обратите внимание, что максимальные значения медиа-запросов имеют неточные значения с дробной частью «.98» в пикселях. Это заметно при выборе Desktop First метода верстки, где максимальная ширина медиа-запроса ограничена. Например, при компиляции Sass «+media-breakpoint-down(lg)» мы получим «@media (max-width: 1199.98px)». Здесь 0.02 пикселя освобождаются для старта следующего медиа-запроса. Имейте это ввиду. В следующих выпусках «Джедай верстки 8» мы рассмотрим этот и множество других моментов из этого урока на реальном примере.</p>
<h2>2. Автоматическая разметка колонок</h2>
<h3>2.1 Колонки одинаковой ширины</h3>
<p>С помощью нового универсального класса «.col» можно указать до 12 колонок в ряду (родитель «.row»), ширина которых будет автоматически вычислена в зависимости от количества элементов и будет равна.</p>
<p>Например:</p>
<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/2-1-kolonki-odinakovoy-shiriny.jpg"/>
<h3>2.2 Установка ширины одной колонки</h3>
<p>Вы также можете явно установить ширину одной колонки, а остальные оставить автоматическими.</p>

```html
<div class="row">
    <div class="col">1 из 3</div>
    <div class="col-6">2 из 3 (широкое)</div>
    <div class="col">3 из 3</div>
</div>
<div class="row">
    <div class="col">1 из 3</div>
    <div class="col-5">2 из 3 (широкое)</div>
    <div class="col">3 из 3</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/2-2-ustanovka-shiriny-odnoy-kolonki.jpg"/>
<p>В данном примере второй элемент в третьем ряду имеет класс «.col-6» и второй элемент во втором ряду имеет класс «.col-5», которые занимают соответствующее количество колонок на всех разрешениях экрана. Ширина остальных колонок является отзывчивой и вычисляется автоматически, занимая всё оставшееся пространство.</p>
<h3>2.3 Контент переменной ширины</h3>
<p>Можно использовать класс «col-{breakpoint}-auto», чтобы определить контент с переменной шириной, в зависимости от занимаемого пространства содержимым колонки. Где breakpoint - размер экрана (xl, lg, md или sm).</p>

```html
<div class="row justify-content-sm-center">
    <div class="col col-md-2">1 из 3</div>
    <div class="col-sm-auto">Контент переменной ширины</div>
    <div class="col col-md-2">3 из 3</div>
</div>
<div class="row">
    <div class="col">1 из 3</div>
    <div class="col-sm-auto">Контент переменной ширины номер два</div>
    <div class="col col-md-2">3 из 3</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/2-3-kontent-peremennoy-shiriny.jpg"/>
<p>
Здесь мы видим, что две центральные колонки занимают ширину, соответствующую ширине содержимого, однако в первом ряду благодаря классу «.justify-content-sm-center» у «.row» весь ряд центрируется и общая ширина зависит только от ширины центральной колонки, в то время, как второй ряд растягивается на всю доступную ширину, но вторая колонка остается фиксированной по ширине содержимого.</p>
<h3>2.4 Мульти-ряд</h3>
<p>Благодаря Bootstrap 4 вы можете сделать в одном ряду несколько строк (переносов). Реализовать это можно с помощью класса «.w-100», который очень похож на тег «br» и по-сути просто делает перенос колонок на новую строку.</p>

```html
<div class="row">
    <div class="col">col</div>
    <div class="col">col</div>
    <div class="w-100"></div>
    <div class="col">col</div>
    <div class="col">col</div>
    <div class="col">col</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/2-4-multi-ryad.jpg"/>

```bash
Обратите внимание, что данный класс является частью дополнительных возможностей Bootstrap 4, которые 
подключаются к проекту отдельно в случае использования Sass версии проекта Bootstrap и находятся в папке
«scss/utilities». Вы также можете подключитьдругие плагины из этой папки к вашему проекту по необходимости.
```

<h2>3. Адаптивные классы</h2>
<h3>3.1 Брейкпоинты</h3>
<p>Очень интересная возможность Bootstrap 4 - возможность задавать универсальные колонки, которые будут отображаться на всех разрешениях. Это упомянутый ранее класс «.col». Кроме того, можно определить класс, указывающий конкретное количество колонок, занимаемое содержимым - это классы с префиксом «.col-{число колонок}», например «.col-6» говорит нам о том, что содержимое займёт 6 колонок из 12. В случае, когда конкретное количество задавать не обязательно, можно смело использовать универсальный класс «.col».</p>

```html
<div class="row">
    <div class="col">col</div>
    <div class="col">col</div>
    <div class="col">col</div>
    <div class="col">col</div>
</div>
<div class="row">
    <div class="col-8">col-8</div>
    <div class="col-4">col-4</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/3-1-breakpoints.jpg"/>

<h3>3.2 На мобильных устройствах</h3>
<p>Вы можете использовать префикс класса «.col-sm-{количество занимаемых колонок}» для того, чтобы задать базовую сетку на всех разрешениях, кроме самых маленьких. На небольших экранах колонки такой сетки будут складываться друг под друга. На разрешениях больше - будут занимать столько места, сколько вы определили в классах.</p>

```html
<div class="row">
    <div class="col-sm-8">col-sm-8</div>
    <div class="col-sm-4">col-sm-4</div>
</div>
<div class="row">
    <div class="col-sm">col-sm</div>
    <div class="col-sm">col-sm</div>
    <div class="col-sm">col-sm</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/3-2-na-mobilnyh.jpg"/>
<p>Здесь мы видим, что первый ряд на устройствах с разрешением более «sm», то-есть больше, чем 576 пикс. разбивается на 2 колонки - шириной 8 и 4 из 12-ти соответственно. Ширина колонок во втором ряду вычисляется автоматически, но на самых малых разрешениях эти колонки также складываются друг под друга, благодаря классу «.col-sm».</p>

<h3>3.3 Создание сложной комбинированной сетки</h3>
<p>С помощью Bootstrap вы можете создавать любые комбинации колонок при создании сетки. Для каждой колонки можно задать любое поведение на различных разрешениях с помощью адаптивных классов. Здесь отличия от третьей версии - только в наименованиях классов.</p>

```html
<!-- На мобильных устройствах: Первая колонка - на полную ширину, вторая на половину -->
<div class="row">
    <div class="col-12 col-md-8">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
</div>

<!-- На десктопе: 3 колонки по 4 в каждой. На мобильных: все колонки вполовину контейнера -->
<div class="row">
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
</div>

<!-- Колонки занимают 6 из 12 колонок на любом разрешении -->
<div class="row">
    <div class="col-6">.col-6</div>
    <div class="col-6">.col-6</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/3-3-sozdaniye-slozhnoy-setki-na-bootstrap.jpg"/>

<h2>4. Выравнивание</h2>
<p>Bootstrap 4 основан на «флексах» и дарит нам все возможности данной модели, которые доступны в простых готовых классах. В числе возможностей - вертикальное и горизонтальное выравнивание.</p>

<h3>4.1 Вертикальное выравнивание</h3>

```html
<div class="row align-items-start">
    <div class="col">Верх</div>
    <div class="col">Верх</div>
    <div class="col">Верх</div>
</div>
<div class="row align-items-center">
    <div class="col">Середина</div>
    <div class="col">Середина</div>
    <div class="col">Середина</div>
</div>
<div class="row align-items-end">
    <div class="col">Низ</div>
    <div class="col">Низ</div>
    <div class="col">Низ</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/4-1-0-bootstrap-4-vertikalnoye-vyravnivaniye.jpg"/>

<p>Помимо управления выравниванием через родительский «.row», можно выравнивать колонки, задавая им соответствующие классы:</p>

```html
<div class="row">
    <div class="col align-self-start">Верх</div>
    <div class="col align-self-center">Середина</div>
    <div class="col align-self-end">Низ</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/4-1-1-bootstrap-4-vertikalnoye-vyravnivaniye-2.jpg"/>

<h3>4.2 Горизонтальное выравнивание</h3>
<p>Кроме того, Bootstrap 4 имеет в своём арсенале инструменты для горизонтального выравнивания колонок при помощи префикса «.justify-content-» у «.row».</p>

```html
<div class="row justify-content-start">
    <div class="col-4">row justify-content-start</div>
    <div class="col-4">row justify-content-start</div>
</div>
<div class="row justify-content-center">
    <div class="col-4">row justify-content-center</div>
    <div class="col-4">row justify-content-center</div>
</div>
<div class="row justify-content-end">
    <div class="col-4">justify-content-end</div>
    <div class="col-4">justify-content-end</div>
</div>
<div class="row justify-content-around">
    <div class="col-4">justify-content-around</div>
    <div class="col-4">justify-content-around</div>
</div>
<div class="row justify-content-between">
    <div class="col-4">justify-content-between</div>
    <div class="col-4">justify-content-between</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/4-2-bootstrap-4-gorizontalnoye-viravnivaniye.jpg"/>

<h3>4.3 Удаление полей между колонками</h3>
<p>Очень часто встречаются ситуации, когда необходимо убрать поля между колонками. Например, если вы создаете галерею и элементы должны быть расположены вплотную, например так:</p>

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/4-3-0-primer-no-gutters.jpg"/>

<p>Для этого достаточно у элемента «.row» задать дополнительный класс «.no-gutters».</p>

```html
<div class="row no-gutters">
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
    <div class="col-6 col-sm-4 col-md-4"><div>col-6 col-sm-4 col-md-4</div></div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/4-3-1-udaleniye-poley-mezhdu-kolonkami.jpg"/>

<h3>4.4 Перенос колонок на новую строку</h3>
<p>Если ряд (.row) заполняется суммарным количеством колонок более 12-ти, последующая колонка переносится на новую строку.</p>

```html
<div class="row">
    <div class="col-9">.col-9</div>
    <div class="col-4">.col-4<br>9 + 4 = 13 колонок - это больше 12. Данный элемент шириной в 4 колонки будет перенесён на новую строку.</div>
    <div class="col-6">.col-6<br>Следующие колонки расположатся вдоль строки.</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/4-4-perenos-kolonok.jpg"/>

```bash
Здесь всё также, как в 3-й версии Bootstrap.
```

<h2>5. Порядок элементов</h2>
<h3>5.1 Классы порядка элементов</h3>
<p>Можно использовать специальные классы с префиксом «.order-» для определения порядка элементов. Если вы знакомы с Flex-вёрсткой, данные правила будут вам знакомы. Bootstrap 4 даёт возможность задавать порядок элементов с помощью классов. Можно задавать порядок напрямую (.order-1.order-md-2):</p>

```html
<div class="row">
    <div class="col">Первый неупорядоченный элемент</div>
    <div class="col order-12">Второй, упорядоченный как последний</div>
    <div class="col order-1">Третий, упорядоченный как первый</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/5-1-0-reordering.jpg"/>

<p>Или можно использовать специальные классы, которые определяют порядок первого и последнего элементов (.order-first, .order-last):</p>

```html
<div class="row">
    <div class="col">Первый неупорядоченный</div>
    <div class="col order-last">Второй, упорядоченный как последний</div>
    <div class="col order-first">Третий, упорядоченный как первый</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/5-1-1-reordering-2.jpg"/>

<h3>5.2 Смещение колонок</h3>
<p>По аналогии с Bootstrap 3, в 4-й версии также есть возможность горизонтального смещения колонок, однако реализовано это несколько иначе и для этого есть специальные классы с префиксом «.offset-».</p>
<h4>5.2.1 Классы смещения</h4>
<p>Сдвигать колонку вправо можно, используя классы «.offset-md-*», которые увеличивают левый отступ на * количество элементов. Из примера ниже, класс «.offset-md-2» сдвинет колонку «.col-md-4» на 2 колонки вправо, остальные примеры работают по аналогии:</p>

```html
<div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4 offset-md-4">.col-md-4 .offset-md-4</div>
</div>
<div class="row">
    <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
    <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
</div>
<div class="row">
    <div class="col-md-6 offset-md-3">.col-md-6 .offset-md-3</div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/5-2-1-offset.jpg"/>

```bash
Можно сбрасывать отступ на всех разрешениях благодаря классу «.offset-*-0», 
где * - это sm, md, lg или xl.
```

<h2>6. Вложенность</h2>
<p>Весьма ожидаемо, что Bootstrap 4 поддерживает вложенность элементов. Работает здесь всё также, как в третьей версии - чтобы вложить колонки в другие, необходимо создать дочерний класс «.row» и уже в него вкладывать колонки.</p>

```html
<div class="row">
    <div class="col-sm-9">Уровень 1: «.col-sm-9»
        <div class="row">
            <div class="col-8 col-sm-6">Уровень 2: «.col-8 .col-sm-6»</div>
            <div class="col-4 col-sm-6">Уровень 2: «.col-4 .col-sm-6»</div>
        </div>
    </div>
</div>
```

<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/6-vlozhennost.jpg"/>
