## API Gateway

##### 1. Покажите на архитектурной диаграмме, где будут располагаться API Gateways.  

![alt tag](https://github.com/reddeveI/sb-architecture/blob/main/images/Api-Gateways.jpg)

Обоснуйте свое решение:
- Для сервисов клиентов, заказов требуется API Gateway, чтобы устранить зависимости клиентских сервисов от сервисов бэкенда, безопасность чтобы пользователи не получили несанкционированный доступ к служебным сервисам. Также плюсом может быть наличие портала с возможностью самообслуживания для разработчиков которые будут интегрироваться с сервисами
- Для сервисов управления производства, сервиса поставщиков, склада материала и контроля качества также требуется API Gateway для достижения "слабой" связности, а не плотной интеграции между внутренними сервисами

##### 2. Для всех добавленных API Gateway опишите, какой функционал они будут предоставлять и по возможности представьте качественные характеристики этого функционала (то есть с цифрами).

- Первый микросервисный API Gateway выступает неким Фасадом между фронтендом и бэкендом, а также для обнаружения и устранения угроз
- Второй микросервисный API Gateway выступает агрегатором сообщений сервисов к складским сервисам для единого формата взаимодействия с ними, а также для наблюдаемости посредством логирования
