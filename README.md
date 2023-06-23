# Пример использования MSW для разработки и тестов

## Полезные ссылки

[Презентация](https://slides.com/sergeyzenin/mocking-api-with-service-workers)

### Service Workers
1. [MDN. Service Worker API](https://developer.mozilla.org/ru/docs/Web/API/Service_Worker_API)
2. [Habr. Service Workers. Инструкция по применению](https://habr.com/ru/companies/2gis/articles/345552/)

### MSW
1. [MSW. Site](https://mswjs.io/)
2. [MSW. Github](https://github.com/mswjs/msw)
3. [MSW. Examples](https://github.com/mswjs/examples/tree/master/examples)

## Работа с приложением
Данная демка, по-сути, приложение из 3-х частей. Имитирует сервис с базой блюд 🧆 и созданием меню на день. Все на заглушках - меню будет одинаковое всегда 🙂 

### client
Клиентская часть на [CRA](https://create-react-app.dev/) с двумя страницами:
1. `/` - Меню на сегодня
2. `/dishes` - Список блюд

### server
Сервис на [fastify](https://www.fastify.io/). Основной бэк.

Есть 2 эндпойнта:
1. GET `/dishes` - отдает список блюд
2. GET `/menu` - отдает меню

### price-sevice
Приложение на [fastify](https://www.fastify.io/). Сервис, который прикручивает цену к блюдам и отдает результат

Есть 2 эндпойнта:
1. GET `/` - получение списка блюд, обогащенных ценой
2. GET `/pretty` - получение списка блюд, обогащенных ценой в читаемом варианте, при запросе через адресную строку браузера
