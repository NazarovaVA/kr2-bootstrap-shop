# Meow Market — интернет-магазин товаров для котов

## Контрольная работа №2

**Тема:** «CSS-фреймворки: разработка интерфейса на Bootstrap или альтернативном CSS-фреймворке».

Проект представляет собой многостраничный сайт интернет-магазина Meow Market, реализованный на CSS-фреймворке Bootstrap 5.3. Предметная область сохраняется: товары для котов (корм, игрушки, лежанки, аксессуары, уход).

## Автор

- **ФИО:** Назарова Виктория Александровна
- **Группа:** ЭФБО-04-25

## Используемый фреймворк

**Bootstrap 5.3.8** (Compiled CSS and JS Bundle).

## Способ подключения

Bootstrap подключён **локально**, без CDN. Файлы фреймворка размещены в папке `vendor/bootstrap/`:

- `vendor/bootstrap/css/bootstrap.min.css`
- `vendor/bootstrap/js/bootstrap.bundle.min.js`

Подключение в `<head>` каждой страницы:

```html
<link rel="stylesheet" href="vendor/bootstrap/css/bootstrap.min.css" />
<link rel="stylesheet" href="css/custom.css" />
```

Bootstrap JS Bundle подключён перед `</body>`:

```html
<script src="vendor/bootstrap/js/bootstrap.bundle.min.js"></script>
```

Локальное подключение позволяет работать с проектом без доступа к интернету и не зависит от доступности CDN.

## Ссылка на опубликованный проект

GitHub Pages: https://nazarovava.github.io/kr2-bootstrap-shop/

## Структура проекта

```
kr2-bootstrap-shop/
├── index.html
├── catalog.html
├── product.html
├── order.html
├── contacts.html
├── css/
│   └── custom.css
├── js/
│   └── main.js
├── data/
│   ├── popular.json
│   └── products.json
├── images/
├── vendor/
│   └── bootstrap/
│       ├── css/bootstrap.min.css
│       └── js/bootstrap.bundle.min.js
├── README.md
└── .gitignore
```

## Используемые технологии

- **Bootstrap 5.3** (сетка, компоненты, утилиты);
- HTML5 (семантическая разметка: `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`);
- CSS3 (внешний файл `custom.css` с фирменными стилями поверх Bootstrap, CSS-переменные в `:root`, Flexbox, CSS Grid);
- JavaScript (рендер товаров из JSON, модальное окно, слайдер шагов, панель с котом);
- Git, GitHub.

## Обязательные страницы

- **index.html** — главная страница: Bootstrap-навигация (`navbar`), hero-блок, преимущества, популярные товары, FAQ, как сделать заказ, отзывы (`carousel`).
- **catalog.html** — каталог: сетка (`container` > `row` > `col-*`), карточки товаров (`card`), фильтры (`form-select`, `form-check`, `form-control`), `alert`.
- **product.html** — карточка товара: описание, характеристики (`table caption-top`), цена, `badge`, `btn`.
- **order.html** — форма заявки (`form-control`, `input-group`, `form-check`), Bootstrap `modal` с подтверждением.
- **contacts.html** — контакты: контактная информация, CTA-блок, встроенная карта.

## Реализованные Bootstrap-компоненты

**Сетка:**

- `container`, `container-fluid`;
- `row`, `col-*`, `col-md-6`, `col-lg-3`, `col-lg-9`, `col-xl-4`;
- отступы через `g-3`, `g-5`.

**Навигация:**

- `navbar`, `navbar-expand-lg`, `navbar-brand`, `navbar-toggler`, `collapse`, `navbar-collapse`, `navbar-nav`, `nav-item`, `nav-link`.

**Карточки:**

- `card` — на страницах index (отзывы), catalog (фильтры и карточки товаров), contacts, а также при рендере популярных товаров из JS.

**Кнопки:**

- `btn`, `btn-primary`, `btn-outline-primary`, `btn-sm`.

**Значки:**

- `badge` — на карточках товаров и на странице товара.

**Сообщения:**

- `alert` — на странице каталога (акция).

**Модальное окно:**

- `modal`, `modal-dialog`, `modal-dialog-centered`, `modal-content`, `btn-close`;
- атрибуты `data-bs-toggle`, `data-bs-target`, `data-bs-dismiss`.

**Формы:**

- `form-control` — все текстовые поля, email, tel, textarea, поля цены;
- `form-select` — сортировка в каталоге;
- `input-group`, `input-group-text` — телефон с префиксом `+7`;
- `form-check`, `form-check-input`, `form-check-label` — чекбокс согласия и фильтры.

**Дополнительные компоненты:**

- `carousel` (`carousel`, `carousel-inner`, `carousel-item`, `carousel-control-prev`, `carousel-control-next`) — карусель отзывов на главной странице.

## Собственный файл custom.css

Файл `css/custom.css` используется для точечной настройки проекта поверх Bootstrap. В нём заданы:

- фирменные CSS-переменные Meow Market (цвета, радиусы, отступы);
- переопределение Bootstrap-переменных (`--bs-primary`, `--bs-link-color`, `--bs-body-color`);
- собственные утилиты (`:where(.card)` — отключает белый фон Bootstrap-карточек, не перебивая кастомные стили);
- стили hero-блока, marquee-строки, карточек товаров, FAQ;
- дополнительные состояния (`:hover`, `:focus-visible`);
- стили модального окна, alert, карусели — в цветах проекта.

`custom.css` **не дублирует** Bootstrap и не переписывает его компоненты — только дополняет.

## Самостоятельные доработки

Сверх базовой части КР №2 реализованы:

- локальное подключение Bootstrap (без CDN);
- дополнительная страница `contacts.html`;
- кастомный дизайн поверх Bootstrap (фирменные цвета Meow Market, пунктирные рамки, шрифт Pacifico);
- адаптивная сетка карточек товаров (`col-md-6` → `col-xl-4`);
- sticky-фильтры в каталоге (`position: sticky`);
- динамический рендер товаров из JSON (`data/products.json`, `data/popular.json`);
- динамический рендер карточки товара по URL-параметру `id`;
- автоподстановка товара и артикула в форму заявки через URL-параметр;
- панель с фото кота (`aside`) и кнопка «Голосование ♥»;
- блок «Интересный факт» с подгрузкой случайного факта о котах;
- кнопка «Наверх» с плавным скроллом;
- marquee-строка с акциями;
- карточки преимуществ с 3D-переворотом;
- анимация печатающегося заголовка.

## Инструкция по просмотру

1. Откройте ссылку GitHub Pages: https://nazarovava.github.io/kr2-bootstrap-shop/
2. Или клонируйте репозиторий:
   ```
   git clone https://github.com/nazarovava/kr2-bootstrap-shop.git
   ```
3. Откройте `index.html` в браузере.

## Текущий статус

Контрольная работа №2 выполнена: все обязательные страницы готовы, Bootstrap подключён локально, реализованы обязательные компоненты и дополнительные доработки.
