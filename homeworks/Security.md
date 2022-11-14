##### 2. Подготовьте схемы компонентов, указав изменения в архитектуре с учётом требований безопасности.
![alt tag](https://github.com/reddeveI/sb-architecture/blob/main/images/Microservices-integration-types-secured.jpg)

##### 1. Для каждой из внешних интеграций распишите векторы атаки и сформулируйте это в виде таблицы, где в соседнем поле будут указаны решения для внедрения.
Описание API/системы	Возможные векторы атак	Способы защиты от векторов атак

|Описание API/системы|Возможные векторы атак|Способы защиты от векторов атак|
|--------------------|----------------------|-------------------------------|
|Сервис заказов|Broken Authentication|Установить время жизни access token - 5 минут, время жизни refresh token 30 минут|
||Insufficient Logging and Monitoring|Фиксировать действия пользователей, реагирование и отправка уведомлений при достижении пороговых значений (Например если пользователь более 5 раз ввёл неправильный пароль блокировать его на 15 минут, если повторно ввёл неправильно, блокировать на сутки)|
||Broken Access Control|Благодаря разграничению доступов ограничиваем каждый сервис, каждое хранилище данных только доступы по соответствующим ролям|
|Сервис заказов|Injections|Использование PreparedStatement чтобы ограничить те данные которые передаются в рамках запроса бд. Не передавать данные пользователя напрямую в бд|
||Broken Authentication|Пользователь может получить доступ к API, но если он узнает адрес сервиса заказов, то сервис заказов должен быть закрыт авторизацией и к нему доступ можно получить только через API. Также внешний сервис службы доставки может получит доступ только к изменению статуса заказа, ко всем остальным методам для него доступ будет закрыт|
||Sensitive Data Exposure|Авторизация только с сервиса, нельзя получить информацию о заказах напрямую. В сервисе проверки заказов установлена проверка на роли, информацию о заказе может получить либо пользователь с ролью администратор, либо пользователь может получить информацию только о своих заказах|
||Broken Access Control|Благодаря разграничению доступов ограничиваем каждый сервис, каждое хранилище данных только доступы по соответствующим ролям|
|Сервис пользователей|Injections|Использование PreparedStatement чтобы ограничить те данные которые передаются в рамках запроса бд. Не передавать данные пользователя напрямую в бд|
||Broken Authentication|Пользователь может получить доступ к API, но если он узнает адрес сервиса пользователей, то сервис пользователей должен быть закрыт авторизацией и к нему доступ можно получить только через API и только после того как пользователь прошёл аутентификацию может получить досутп к своим данным. Для менеджеров досут к данным пользователем будет с замаскированными данными с особо важной информацией|
||Sensitive Data Exposure|Пользовательские данные самые чувствительные, поэтому должны быть максимально защищены. Пользователь может получить информацию только о своей учётной записи. Менеджеры и администратор могут получить доступ только в замаскированном виде чувствительных данных. Если администратор хочет получить полные данные о пользователи, должен пройти двухфакторную авторизацию|
||Broken Access Control|Благодаря разграничению доступов ограничиваем каждый сервис, каждое хранилище данных только доступы по соответствующим ролям|
|Сервис продуктов|Injections|Использование PreparedStatement чтобы ограничить те данные которые передаются в рамках запроса бд. Не передавать данные пользователя напрямую в бд|
||Broken Authentication|Доступ к чтению данных может быть открытым, а доступ к записи и изменению только для пользователей с ролью администратор и менеджер|
||Sensitive Data Exposure|В этом сервисе отсутстуют чувстительные пользовательские данные|
||Broken Access Control|Благодаря разграничению доступов ограничиваем каждый сервис, каждое хранилище данных только доступы по соответствующим ролям|