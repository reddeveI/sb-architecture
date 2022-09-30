# Бизнес-кейс
FlaminGo — это бесплатная доставка продуктов с высокой зоной покрытия по городу Алматы. Продукты находятся на складах, где собираются и передаются курьерам на доставку.

# Детализация бизнес-целей <a name="bn_details"></a>
Бизнес-цели приложения:
* Увеличение количества заказов
* Повышение узнаваемости бренда

# Требования к системе

## Роли пользователей
* **UR-1**: Администратор 

**SECTION** | READ | CREATE | UPDATE | DELETE |
-----------|------|-------|--------|--------|
Аналитика |<div align="center">:white_check_mark:</div>||||
Заказы |<div align="center">:white_check_mark:</div>||<div align="center">:white_check_mark:</div>||
Товары |<div align="center">:white_check_mark:</div>||<div align="center">:white_check_mark:</div>||
Управление баннерами |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление сторис |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление скидками |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление положением категорий |<div align="center">:white_check_mark:</div>||<div align="center">:white_check_mark:</div>||
Управление FAQ |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление промокодами |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление сторис для категорий |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление рассылками |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление рекомендованными товарами|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Правила соглашения |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление пользователями |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>||
                    
                    
* **UR-2**: Менеджер

**SECTION** | READ | CREATE | UPDATE | DELETE |
-----------|------|-------|--------|--------|
Аналитика |<div align="center">:white_check_mark:</div>||||
Управление баннерами |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление сторис |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление скидками |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|
Управление положением категорий |<div align="center">:white_check_mark:</div>||<div align="center">:white_check_mark:</div>||
Управление пользователями |<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>|<div align="center">:white_check_mark:</div>||

* **UR-3**: Фасовщик

**SECTION** | READ | CREATE | UPDATE | DELETE |
-----------|------|-------|--------|--------|
Заказы |<div align="center">:white_check_mark:</div>||<div align="center">:white_check_mark:</div>||
Товары |<div align="center">:white_check_mark:</div>||<div align="center">:white_check_mark:</div>||

* **UR-4**: Пользователь

## Анализ и список функциональных требований <a name="func_req"></a>
Пользователь, здесь и далее - зарегистрированный в приложении человек с номером телефона и id в системе

* **FR-1**: **Главная страница приложения**:
    - Пользователь может первично авторизоваться в приложении введя номер телефона и код из смс (UR-4);
    - Пользователь должен видеть вверху главной страницы перелистывающийся баннер с промо, поле поиска продуктов, сторис, ограниченный список скидочных продуктов, список категорий и кнопку перелистать наверх (UR-4);
* **FR-2**: **Управление пользователями**:
    - Администратор может зарегистрировать пользователя админ панели по электронной почте, указать роль, создать пароль для первого входа, сбросить пароль и деактивировать учётную запись (UR-1)
    - Менеджер/Фасовщик может изменить ФИО и пароль своей учётной записи (UR-2, UR-3)
    - Пользователь может в настройках профиля добавить/изменить имя, почту и привязать/отвязать аккаунт социальных сетей (UR-4);
    - Пользователь может управлять разрешениями для получения пуш нотификаций и маркетинговых рассылок (UR-4);
    - Пользователь может сохранять/удалять адреса (UR-4);
    
* **FR-3**: **Управление товаром**:
    - Администратор может просмотреть список товаров, изменить название, категорию, описание и установить скидку (UR-1)
    - Администратор может добавить/удалить товар в список популярных (UR-1)
    - Пользователь может просмотреть список товаров по категориям (UR-4)
    - Пользователь может добавить товар в избранное (UR-4)

* **FR-4**: **Управление заказом**:
    - Администратор может просматривать список завершённых, активных и необработанных всех заказов (UR-1)
    - Фасовщик может просматривать список завершённых, активных и необработанных заказов относящихся к его складу (UR-3)
    - Пользователь может просматривать список завершённых и активных заказов, а также детали заказа, сумму заказа и время выполнение заказа (UR-4)
    - При формировании заказа пользователь может ввести адрес либо выбрать из списка созранённых адресов (UR-4)

* **FR-5**: **Корзина**:
    - Пользователь может добавлять/удалять товары в корзину (UR-4)
    - Пользователь может видеть сумму заказа в корзине (UR-4)

* **FR-6**: **Оплата**:
    - Пользователь может ввести данные банковской карты либо выбрать из списка сохранённых карт (UR-4)
    - Пользователь может добавить карту в список сохранённых (UR-4)
    - В момент оплаты пользователь может ввести промокод для получения скидки (UR-4)
    - На странице оплаты пользователь должен видеть таймер обратного отсчёта (UR-4)

* **FR-7**: **Аналитика**:
    - Администратор/менеджер должен аналитику продаж и активности на главной странице админ панели (UR-1)

* **FR-8**: **Уведомления**:
    - Администратор/менеджер может отправлять маркетинговые рассылки определённым группам пользователей (UR-1)
    - Пользователь может получить уведомление о новостях, акции или скидке только если дал на это соответствующее согласие в лично кабинете (UR-4)

# Целевая архитектура

![alt tag](https://github.com/reddeveI/sb-architecture/blob/main/images/C4Context.drawio.png)
