# Bootstrap 4. Сетка. Подробное руководство
<h2></h2>
<h3></h3>
<p></p>
<img src="https://webdesign-master.ru/img/blog/html-css/bootstrap-4/1-1-grid-options.jpg"/>
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
```bash
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
