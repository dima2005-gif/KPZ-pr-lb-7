# Величко Дмитро ІПЗ 3.02
## Практично-лабораторне заняття №7
## Інтеграція клієнтської частини з RESTful API

Скопіюємо з 6 практичної роботи наш проект. Наш бек проект це той проект який був створений у ході 3-4 лабораторній, практичних роботах. 
### Back end
Відкриємо його і перш за все зайдемо у файл ```.env```.

Тут звертаємо увагу на рядок ```JWT_EXPIRATION```, за дефолтом тут стоїть 15 хвилин, змінюємо це значення на 60 хвилин.
![env_jwt](https://github.com/user-attachments/assets/ee4b2e12-e235-4a54-9605-d745cf945132)

Тепер якщо у нас докер контейнери є, то запускаємо Docker.

Після запуску запускаємо наш бекенд, за допомогою команди: ```npm run dev```

Після цього переходимо у Postman і робимо запит у каталозі ```auth\login``` ```POST``` запит для отримання токена.

![postman_token](https://github.com/user-attachments/assets/c21ecbd6-1d05-4388-a419-7634dbea83c4)


Тепер цей токен ставимо у файл ```.env``` у фронт-енді.

### Front end

Тепер відкриємо його. Додакмо у файл ```.env``` і вставимо такі рядки перше з яких це локальна адреса, а другий наш токен.

![env_front](https://github.com/user-attachments/assets/dc90b348-1353-4815-a865-28f53953047b)

Далі створюємо файл ```index.ts``` у каталозі ```api``` який у свою чергу знаходиться у каталозі ```src```.
![src_api_index](https://github.com/user-attachments/assets/729b9888-52e3-498a-9555-ad6e4ce80751)

Вставимо у цей файл ось такий зміст
![index_api](https://github.com/user-attachments/assets/bca1ceb8-f37a-451b-be8a-d9d0245de4cc)

АЛЕ перед цим додамо залежність axios. Для цього виконаємо команду: ```npm add axios```

Тепер перейдемо у файл у ```/pages/Entities.tsx``` і додамо дещo

![entities_1](https://github.com/user-attachments/assets/192e18ff-8ec5-4c13-9515-a50583248b99)
![entities_2](https://github.com/user-attachments/assets/7fddc2ff-491c-4037-b27f-fe86df5799ee)
![entities_3](https://github.com/user-attachments/assets/2dac3c10-d165-448d-84a9-fc956fe946e3)
![entities_4](https://github.com/user-attachments/assets/5b324642-cbf4-4080-be2b-795a1c7f6932)

Тепер перейдемо у файл у ```/pages/EntityCreate.tsx``` і додамо дещo

![entity_create_1](https://github.com/user-attachments/assets/5c1c825b-96fe-4f45-99f5-c4e25e879817)
![entity_create_2](https://github.com/user-attachments/assets/1f26d9a1-ba41-4bcd-9abb-706b639f2309)
![entity_create_3](https://github.com/user-attachments/assets/97c8892d-797c-4326-80a9-9ef0d6bf5cde)


Тепер перейдемо у файл ```index.ts``` який знаходиться у файлі ```entities```
![index_1_entities](https://github.com/user-attachments/assets/5451f473-a983-4629-bea2-d56cec3e44fc)
![index_2_entities](https://github.com/user-attachments/assets/d5476714-b49c-4906-95b9-18b952c651d6)
![index_3_entities](https://github.com/user-attachments/assets/002a6918-3767-4c0a-95a6-655db70c2986)
![index_4_entities](https://github.com/user-attachments/assets/428fabbd-3901-48aa-86b5-b5bd59861f6b)

Все тепер з фронт-ендом усе.
Запустимо його за допомогою команди: ```pnpm run dev```

### Тепер результат:
## Ось наші сутності

![check_list](https://github.com/user-attachments/assets/06eb83e5-4eeb-4ed8-9e92-f7eaeb18825e)

## Тепер спробуємо замінити сутності, тобто змінити їхній зміст

![check_update](https://github.com/user-attachments/assets/c244c445-35e3-4cf3-981f-ac98b9e22cf3)

## Перевіримо паралельно на Postman

![check_update_postman](https://github.com/user-attachments/assets/1570ab04-62d3-4d7d-8952-5d160182eed6)


## Тепер перевіремо створення нової сутності
![create_new](https://github.com/user-attachments/assets/54b8d7d3-a1c7-4cc7-ba61-1d98c2a9af93)

## Тепер перевіяємо чи з'явився він у списку
![check_create_new](https://github.com/user-attachments/assets/ec68d264-7da0-4ae2-8d56-07bc5c7adcca)

## Тепер на Postman
![check_create_new_postman](https://github.com/user-attachments/assets/49ab260f-b6bc-4d0f-9ef0-7976bcfffea4)

## Тепер перевіремо видалення сутностей
Видалемо сутність ```Dima Velichko```

![check_delete](https://github.com/user-attachments/assets/3e3e04c8-8fbf-4179-914c-5ea2bf15629d)

## Тепер у Postman
![check_delete_postman](https://github.com/user-attachments/assets/7237a68d-f9d6-43b2-bfc8-6b3ec3cef8d0)

Як басимо усі операції CRUD  працюють вдало.

## Загальний висновок

У результаті роботи було успішно реалізовано інтеграцію клієнтської частини з RESTful API. Було повторно використано попередні проєкти з бекенду та фронтенду, налаштовано середовище, оновлено змінні конфігурації у `.env` файлах, а також підключено бібліотеку `axios` для зручної роботи з HTTP-запитами.

На стороні фронтенду були реалізовані функціональні компоненти, які дозволяють виконувати всі базові операції CRUD (створення, читання, оновлення, видалення) над сутностями. Усі ці дії були перевірені як через інтерфейс додатку, так і через Postman для підтвердження коректності обміну даними з API.

Таким чином, інтеграція клієнтської частини з серверною була виконана успішно, що підтверджується стабільною роботою усіх CRUD-операцій та синхронізацією даних між фронтендом і бекендом.
