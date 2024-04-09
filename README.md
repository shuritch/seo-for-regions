<h1 align="center">
Гибридное региональное продвижение без потерь и больших затрат
</h1>

<img height="180" width="259" src="./assets/cities.gif" align="left" />

На одном из недавних проектов снова встал вопрос регионального продвижения. Проект, уже имел региональный функционал на основе поддоменов. Но нас он не устраивал, об этом и как мы нашли **win-win** способ для поисковиков от **Yandex** и **Google**.

Не берусь судить об эффективности этого метода, он был опробован только на одном проекте и хотя это дало необходимые результаты - это не значит что это сработает и в вашей ситуации.

---

## Существующие подходы

> [!TIP]
> Вы можете пропускать разделы, знакомые вам и сразу перейти к моей [находке](#моя-находка-или-гибридный-подход), однако я вам рекомендую освежить память, а возможно и узнать что-то новое.

Здесь мы не будем рассматривать все подходы, например, подход с внедрением множества региональных ключевых слов в страницу мы обойдем стороной. Все рассматриваемые способы в этой статье - создают отдельный контент под конкретный город или регион.

### Доменная региональность

<img height="180" width="259" src="./assets/webmaster-regions.png" align="left"/>

Возможно это самый популярный сейчас подход по региональному продвижению в СНГ. Все это из-за популярности у нас поисковой системы от **Yandex**, который предоставляет функционал для определения региона доменна прямо из своей панели **Yandex webmaster**.

<br/>
<br/>
<br/>
<br/>

На данный момент, поисковик **Yandex** отдает предпочтение бизнесу, который закрепился локально в конкретном регионе. Конечно, не всем и не всегда, все зависит от качества и прочих переменных.
Но определенный прирост в этом есть, если использовать региональные ключи - можно получить гео-зависимые запросы.
Возможно вы уже видели сайт с похожими доменами:

- spb.website.ru
- krasnodar.website.ru
- volgograd.website.ru
- И другие

Такие веб-сайты используют доменный способ регионального продвижения. <br/>
Приведу пример:

<p align="center">
  <img width="300px" height="225px" hspace="10" src="./assets/subdomain-krasnodar.png" />
  <img width="300px" height="225px" hspace="10" src="./assets/subdomain-spb.png" />
</p>

Здесь я подчеркнул веб-сайты, которые как раз продвигаются этим способом, например **Cian.ru**. Однако мне повезло и на примерах видно и второй тип регионального продвижения - **Avito.ru** и **realty.ya.ru** используют [региональность на основе вложенности](#региональность-на-основе-вложенности).

### Региональность на основе вложенности

Есть несколько вариантов реализации данного подхода, например:

#### Версия №1 - Регион-директория

```graphql
/ # Главная страница
/about# О Веб-сайте / Гео-независимые страницы
/products # Предоставляемые услуги / товары
  ├─ /buy-sony-tv # Конкретный товар 1, содержащий ключевые слова по Москве
  └─ /buy-samsung-phone # Конкретный товар 2, содержащий ключевые слова по Москве
/spb
  ├─ / # Копия Главной страницы с обновленными региональными ключами
  ├─ /products
  │  ├─ /buy-sony-tv # Конкретный товар 1, содержащий ключевые слова по другому городу
  │  └─ /buy-samsung-phone # Конкретный товар 2, содержащий ключевые слова по другому городу
  └─ /about # Закрыто от индексации, чтобы не дублировать контент
/krasnodar
  ├─ / # Копия Главной страницы с обновленными региональными ключами
  ├─ /products
  │  ├─ /buy-sony-tv # Конкретный товар 1, содержащий ключевые слова по другому городу
  │  └─ /buy-samsung-phone # Конкретный товар 2, содержащий ключевые слова по другому городу
  └─ /about # Закрыто от индексации, чтобы не дублировать контент
```

#### Версия №2 - Регион как часть URL услуги

```graphql
/ # Главная страница
/about# О Веб-сайте / Гео-независимые страницы
/products # Предоставляемые услуги / товары
  ├─ /buy-sony-tv
  ├─ /buy-sony-tv-in-spb
  ├─ /buy-sony-tv-in-krasnodar
  └─ etc
```

### Моя находка или Гибридный подход

- В процессе

#### Настраиваем доменный подход

- В процессе

#### Настраиваем вложенный подход

- В процессе

## Итоги

Надеюсь, после моего рассказа гибридное региональное продвижение перестанет быть для вас чем то радикальным или диким.

**Уважаемые читатели!** Известно ли вам что-то такое о региональном, о чём мало кто знает?, если так - просим поделиться своим мнением.
