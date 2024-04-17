<h1 align="center">
Улучшаем региональное SEO продвижение сайта
</h1>

<img height="180" width="259" src="./assets/cities.png" align="left">

На одном из недавних проектов снова встал вопрос регионального продвижения. Проект уже имел региональный функционал на основе поддоменов. О том что нас не устраивало и как мы нашли **win-win** способ для поисковиков от **Yandex** и **Google**.

Не берусь судить об эффективности этого метода, он был опробован только на одном проекте и хотя это дало необходимые результаты - это не значит что метод сработает и в вашей ситуации.

---

## Разбираемся в существующих подходах

> [!TIP]
> Вы можете пропускать знакомые вам разделы и сразу перейти к [самому важному](#моя-находка-или-гибридный-подход), однако я вам рекомендую освежить память, а возможно даже узнать что-то новое.

Здесь мы не будем рассматривать все подходы, например, подход с внедрением множества региональных ключевых слов в страницу мы обойдем стороной. Все рассматриваемые способы в этой статье - создают отдельный ресурс под конкретный город или регион.

Также я не хотел здесь глубоко уходить в технические детали, для понимания этого не потребуется. Однако материал содержит код, так что... приступим !

### Доменная региональность

<img width="259" src="./assets/webmaster-regions.png" align="left"/>

Возможно, сейчас это самый популярный подход по региональному продвижению в СНГ. В основном это из-за популярности поисковой системы **Yandex**, которая предоставляет функционал для определения точного региона домена из своей панели **Yandex webmaster**. Домены с определенным регионом обладают повышенным приоритетом _по гео-зависимым запросам_.

Однако есть и **минус**, в похожем функционале от Google - на выбор есть только регион "Россия", из-за чего подход показывает себя значительно хуже.

<div align="center">

| Характеристика <img width="441" height="1"> | Личный показатель |
| :------------------------------------------ | :---------------: |
| Простота разработки                         |        😴         |
| Безопасность от санкций                     |        🏰         |
| Скорость развития домена                    |        🐢         |
| Эффективность в поисковике Яндекс           |        🔥         |
| Эффективность в поисковике Google           |        💀         |

</div>

> [!TIP]
> Лучше всего подход работает когда ваш разработчик настроил wildcard домен третьего уровня с перенаправлением на один сервер всех `*.website.ru` адресов, где название поддомена обрабатывается как переменная для отбора нужных ключей.
>
> В своей практике я не раз сталкивался с неправильным способом реализации - когда доменную региональность реализовывали с помощью нескольких веб-серверов, каждый под свой поддомен. Такой подход чаще всего приводит к неоправданным **расходом** и **увеличенному TTM**.

Таким образом, создав множество поддоменов или даже уникальных доменов, можно ухватить большое количество гео-зависимых запросов почти бесплатно.
Возможно вы уже видели сайт с похожими доменами:

<p align="center">
<b>spb</b>.website.ru • <b>krasnodar</b>.website.ru • <b>volgograd</b>.website.ru • <b>rostov</b>.website.ru
</p>

<p align="center">
  <img width="390px"  hspace="10" src="./assets/subdomain-krasnodar.png" />
  <img width="390px"  hspace="10" src="./assets/subdomain-spb.png" />
</p>

Здесь я подчеркнул веб-сайты, которые как раз продвигаются этим способом, например **Cian.ru**. Однако мне повезло и на примерах видно и второй тип регионального продвижения - **Avito.ru** и **realty.ya.ru** используют [региональность на основе вложенности](#региональность-на-основе-вложенности).

> [!WARNING]
> Одного выбора региона не достаточно, ваши поддомены также должны содержать специфичные для региона ключевые слова и информацию. Также стоит использовать разную контактную информация для лучшей обработки лидов.

### Региональность на основе вложенности

Вся суть данного способа заключается в создании региональных страниц, а каким образом они будут распределены, уже зависит от исполнения.

> [!TIP]
> Стоит отметить, что эффективность в поисковой системе Яндекс чаще всего себя не оправдывает. За исключением тех случаев, когда вы имеете реальные адреса в регионах и они зарегистрированы в Яндекс справочнике.

<div align="center">

| Характеристика <img width="441" height="1"> | Личный показатель |
| :------------------------------------------ | :---------------: |
| Простота разработки                         |        ⏰         |
| Безопасность от санкций                     |        💩         |
| Скорость развития домена                    |        🐇         |
| Эффективность в поисковике Яндекс           |        ❓         |
| Эффективность в поисковике Google           |        🔥         |

</div>

#### Версия №1 - Регион-директория

Эту версию также называют зеркальным методом, основной идеей является создание зеркал всех маршрутов от главной страницы в региональных директориях. Также необходимо разделить ваши страницы на гео-зависимые и гео-независимые, чтобы потом исключить из индексации зеркальные версии последних. Примерная структура:

```graphql
/         # Главная страница
/about    # Гео-независимые страницы
/products # Гео-зависимые страницы, ключи по городу Москва
  ├─ /buy-sony-tv
  └─ /buy-samsung-phone
/spb
  ├─ /         # Зеркало главной страницы с обновленными региональными ключами
  ├─ /products # Гео-зависимые страницы, ключи по городу Санкт-Петербург
  ├─ /about    # Закрыто от индексации, чтобы не дублировать контент
  │  ├─ /buy-sony-tv
  │  └─ /buy-samsung-phone
  └─ ...
/krasnodar
  ├─ /         # Зеркало главной страницы с обновленными региональными ключами
  ├─ /products # Гео-зависимые страницы, ключи по городу Краснодар
  ├─ /about    # Закрыто от индексации, чтобы не дублировать контент
  │  ├─ /buy-sony-tv
  │  └─ /buy-samsung-phone
  └─ ...
```

> [!WARNING]
> Тогда как прошлый способ не требовал почти никаких доработок, эта версия в них нуждается:
>
> - Стоит добавить функционал выбора города и уточнения текущего у пользователя.
> - Sitemap.xml должен сам перестраиваться в зависимости от состояния страниц.
> - Необходимо исключить повторяющиеся гео-независимые страницы из индексации.
> - Также можно внедрить умные ссылки, чтобы сами подстраивались под регион и не давали пользователю его случайно переключить.
> - Для лучшей навигации можно внедрить HTML Карту сайта с перечислением всех городов и их внутренних ссылок.

Пример конфига Robots.txt для данного способа:

```txt
User-agent: *
Disallow: /city-*/  # Закрываем регионы (позже откроем нужные страницы)
Allow: /*service-   # Открываем зеркальные услуги
Allow: /*catalog-   # Открываем зеркальные каталоги
Allow: /city-*/ceny # Открываем зеркальный список цен
Disallow: /api      # Закрываем служебные страницы
Disallow: /search   # Закрываем поиск
Disallow: /*?       # Закрываем копии с параметрами

Sitemap: https://website.ru/sitemap.xml
```

#### Версия №2 - Регион-страница

Чаще всего эта версия попадается на интернет-барахолках, где пользователи сами выставляют товар на продажу. Так как нет четкого представления о регионах веб-сайта, он приписывается каждому товару по отдельности самим пользователем, а система добавляет его в мета-теги и текста, а иногда и в URL. Примерная структура:

```graphql
/                              # Главная страница
/about                         # О Веб-сайте / Гео-независимые страницы
/products                      # Предоставляемые услуги / товары
  ├─ /buy-sony-tv              # Гео-независимый товар
  ├─ /buy-sony-tv-in-spb       # Гео-зависимый товар
  ├─ /buy-sony-tv-in-krasnodar # Гео-зависимый товар
  └─ /buy-item-I1234567S890    # Не ЧПУ
```

Причем в конечном итоге не так важно используются у вас ЧПУ ссылки или их названия придумали пришельцы, так-как самое главное - внедрить региональный ключ в страницу и придумать уникальный URL адрес.

## Моя находка или Гибридный подход

<img height="150" width="150" src="./assets/tests.jpg" align="left">

Оба предыдущих подхода действительно хороши, однако, ни один из них не продвигается одинаково хорошо в ПС от Yandex и Google. Меня это не устраивало, и, изучив подробно оба способа, я не нашел ни одной причины не использовать их одновременно.

Однако, по какой-то неведомой мне причине, я не нашел ни одного упоминания данного способа. И **тщательно** все взвесив - я решил экспериментировать !

### Проектируем

В проекте уже использовался доменный метод регионального продвижения, так что оставалось лишь ввести второй способ и настроить правильную индексацию, чтобы не нарушить уникальности контента и избежать санкций от поисковых систем. Исходя из моей логики, мы должны были получить:

<div align="center">

| Характеристика <img width="441" height="1"> | Доменный подход | Зеркальный подход | Гибридный подход |
| :------------------------------------------ | :-------------: | :---------------: | :--------------: |
| Простота разработки                         |       😴        |        ⏰         |     😴+⏰=🩹     |
| Безопасность от санкций                     |       🏰        |        💩         |     🏰+💩=🩹     |
| Скорость развития домена                    |       🐢        |        🐇         |     🐢+🐇=🩹     |
| Эффективность в поисковике Яндекс           |       🔥        |        ❓         |     🔥+❓=🩹     |
| Эффективность в поисковике Google           |       💀        |        🔥         |     💀+🔥=🩹     |

</div>

### Внедряем вложенную региональность

Я решил использовать региональный каталог, так-как мне он показался проще в реализации и дешевле в дальнейшей эксплуатации. В проекте используется компонентно-ориентированный фреймворк **SvelteKit**, который позволил мне запросто реализовать эту логику.

Таким образом появился каталог `/city-*`, который полностью отражал все корневые маршруты. Так, например, страницы `/city-spb` и `/city-spb/cleaning-service` стали зеркалами главной страницы и страницы услуги чистки соответственно, однако уже использовали ключевые слова города Санкт-Петербург.

Помимо этого, я внедрил _Умные ссылки_, _HTML Карту сайта_ и обновил _sitemap.xml_, а также настроил _городской выбор_ на один домен, но об этой рутине как-нибудь в другой раз...

### Настраиваем правильную индексацию

Самая главная сложность данного подхода - настройка правильной индексации, так-как ошибившись, мы рискуем потерять уникальность контента, а как следствие - получить санкции от поисковых систем. С моей точки зрения, правильная индексация для данного подхода наступит при:

- Закрытых от индексации вложенных регионов Яндексом
- Закрытых от индексации поддоменов другими Поисковыми системами
- Не запутавшимся во всем этом разработчике

Таким образом, я написал стандартную конфигурацию файла **Robots.txt**, которая будет работать на основном домене. Благодаря такой конфигурации, я смог добиться исключения из индексации всей логики вложенных регионов для ПС Yandex, а также исключить _все вложенные гео-независимые страницы_ для остальных поисковых систем.

```txt
# Robots.txt
# website.ru

# Роботы Яндекса
User-agent: YandexBot
User-agent: Yandex
Disallow: /api
Disallow: /search
Disallow: /*?*
Disallow: /city-*

# Остальные роботы
User-agent: *
Disallow: /city-*/
Allow: /*service-
Allow: /*catalog-
Allow: /city-*/ceny
Disallow: /api
Disallow: /search
Disallow: /*?*

Sitemap: https://website.ru/sitemap.xml
```

> [!TIP]
> Директива `Disallow: /city-*` закрывает все вложенные регионы. Однако, нам такое поведение подходит только для роботов Яндекса. Чтобы исключить только гео-независимые страницы, я также прописываю директивы `Allow: /*service-`, `Allow: /city-*/prices`, `Allow: /*service-`, которые открывают только гео-зависимые страницы для индексации прочими поисковыми роботами.

Но этого не достаточно, также нужно закрыть поддомены от поисковых роботов Google и прочих поисковых систем, чтобы оставить данный способ продвижения для поисковых роботов Яндекса. Таким образом получилась еще одна конфигурация, которая будет доступна со всех поддоменов:

```txt
# Robots.txt
# *.website.ru
# (spb.website.ru, krasnodar.website.ru, etc)

User-agent: YandexBot
User-agent: Yandex
Disallow: /api
Disallow: /poisk
Disallow: /*?*
Disallow: */cdn-cgi
Disallow: /gorod-*

User-agent: *
Disallow: /

Sitemap: https://*.website.ru/sitemap.xml
```

> [!WARNING]
>
> Строка `Sitemap: https://*.website.ru/sitemap.xml` из примера содержит невалидный синтаксис и используется только для показательной цели.

### Проверяем результаты нашей работы

После 3 месяцев работы данного способа - мы решили подвести итоги. Для этого мы решили сравнить временные отрезки за Октябрь-Декабрь и Январь-Март. Однако, прежде чем смотреть статистику, стоит сказать - в проекте не используется реклама, а также, за этот период мы ввели много других улучшений, например: семантическую верстку, микроразметку, а также оптимизации разных видов.

<img src="./assets/oct-dec.jpg" />
<p align="right"><i>Октябрь-декабрь</i></p>
<img src="./assets/jan-mar.jpg" />
<p align="right"><i>Январь-Март</i></p>

Как видно из статистики, количество посетителей из поисковой системы гугла не только сравнялось с посетителями из Яндекса, но и даже обогнало. Такой эффект почти никогда не проявляется при доменном подходе. Однако, напомню, эта статистика непоказательна и служит лишь в качестве оправдания данной статьи.

Исходя из моего личного опыта, подход себя проявляет:

<div align="center">

| Характеристика <img width="441" height="1"> | Доменный подход | Зеркальный подход | Гибридный подход |
| :------------------------------------------ | :-------------: | :---------------: | :--------------: |
| Простота разработки                         |       😴        |        ⏰         |     😴+⏰=🤡     |
| Безопасность от санкций                     |       🏰        |        💩         |     🏰+💩=🏠     |
| Скорость развития домена                    |       🐢        |        🐇         |     🐢+🐇=🧟     |
| Эффективность в поисковике Яндекс           |       🔥        |        ❓         |     🔥+❓=💰     |
| Эффективность в поисковике Google           |       💀        |        🔥         |     💀+🔥=💰     |

</div>

## Итоги

Таким образом, у меня удалось обеспечить веб-сервис сразу двумя способами регионального продвижения, благодаря чему я получил хорошие показатели в поисковых системах от **Yandex** и **Google**.

**Уважаемые читатели!** Известно ли вам что-то такое о региональном SEO, о чём мало кто знает? Если так - просим поделиться своим мнением.
