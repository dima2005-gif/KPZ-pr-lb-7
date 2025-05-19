# Величко Дмитро ІПЗ 3.02
## Практично-лабораторне заняття №7
## Інтеграція клієнтської частини з RESTful API

Скопіюємо з 6 практичної роботи наш проект. Наш бек проект це той проект який був створений у ході 3-4 лабораторній, практичних роботах. 
### Back end
Відкриємо його і перш за все зайдемо у файл ```.env```.

![env_jwt](https://github.com/user-attachments/assets/cb237c35-2943-46b1-9d2d-1a7bf87ef71d)

Тут звертаємо увагу на рядок ```JWT_EXPIRATION```, за дефолтом тут стоїть 15 хвилин, змінюємо це значення на 60 хвилин.


Тепер якщо у нас докер контейнери є, то запускаємо Docker.

Після запуску запускаємо наш бекенд, за допомогою команди: ```npm run dev```

Після цього переходимо у Postman і робимо запит у каталозі ```auth\login``` ```POST``` запит для отримання токена.

![postman_token](https://github.com/user-attachments/assets/aa043d1b-0bcc-441e-9300-2b3c5d98a95d)


Тепер цей токен ставимо у файл ```.env``` у фронт-енді.

### Front end

Тепер відкриємо його. Додакмо у файл ```.env``` і вставимо такі рядки перше з яких це локальна адреса, а другий наш токен.

![env_front](https://github.com/user-attachments/assets/46c77ffb-e4b0-4907-a53c-3be9fd3109c1)


Далі створюємо файл ```index.ts``` у каталозі ```api``` який у свою чергу знаходиться у каталозі ```src```.

![src_api_index](https://github.com/user-attachments/assets/e948ce1a-0a3f-4c3b-a89f-7374341c50c4)

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
# Початкова сторінка

![start_page](https://github.com/user-attachments/assets/8c456e4e-cfe0-4381-9ca8-0fc605aeebfa)

Тепер створемо декілька сутностей.

# Створення сутності Create
Для цього натиснемо кнопку `Створити новий екземпляр`

![page_create](https://github.com/user-attachments/assets/7b861990-4c22-4555-b814-2c086e0cae7f)

Натискаємо кнопку `Створити`.

Ось початкова сторінка з нашою сутністю.

![create_entities](https://github.com/user-attachments/assets/98cc921b-ffde-4105-91e0-9feaed051910)

Перевіримо у pgAdmin таблицю `post`

# До

![before_create_entities](https://github.com/user-attachments/assets/fcea6ef5-a2a9-47dc-8481-1deb5f45c652)

# Після

![after_create_entities](https://github.com/user-attachments/assets/3aaa1b40-cded-49a2-99ef-506495c76105)

Cтворемо ще пару сутностей.

# Перегляд сутності Read

Ось наша сторінка з сутностями

![main_page](https://github.com/user-attachments/assets/576a11f7-44f9-4b04-8959-14ef63c489f2)

В PostgreSQL

![pgadmin_for_read](https://github.com/user-attachments/assets/892994f0-81b9-4f3e-bede-ad8f5751d198)

Так прочитаємо дельтано про сутність `Dima Velichko`, для цього натиснемо кнопку `Детально`

![read_entities](https://github.com/user-attachments/assets/ba7738d9-f0c1-44e2-a8ed-dcec12b93d5b)

Переглянемо, що у консолі. Для цього натиснемо `F12`

![console](https://github.com/user-attachments/assets/ecf71ceb-ef48-4c2c-96e5-756f168c66ab)

Тепер якщо ми натиснемо на конкретну сутність аби переглянути детально:

![console_read](https://github.com/user-attachments/assets/b22cbfc5-eafa-4303-8b4f-22540a10e6aa)

# Оновлення сутності Update
Нехай ми оновимо сутність `Vlad Ladanyak`, натиснемо кнопку `Редагувати`, але перед цим зафіксуємо попередній стан.

Сайт і консоль

![page_before_update](https://github.com/user-attachments/assets/d13a17a9-580f-450a-b7b2-8de81775f5bf)

PostgreSQL

![pgadmin_for_read](https://github.com/user-attachments/assets/ca8098e8-9b1c-4166-8ac7-7e0deb3e792b)

Тепер можемо редагувати.

# До

![before_update_name](https://github.com/user-attachments/assets/13ecb4e4-19d4-476e-b962-1a5a0556166c)

![before_update_desc](https://github.com/user-attachments/assets/08567cb5-0efc-4f06-9cd7-7b9b26ba8aef)

# Після

![after_update_name](https://github.com/user-attachments/assets/2370a5dd-adea-4a9d-83d0-1842dd69cbeb)

![after_update_desc](https://github.com/user-attachments/assets/0184b589-5756-4731-abc4-e2f6d3703e3d)

Повідомлення про успішність оновлення

![update_success](https://github.com/user-attachments/assets/b9b5ac94-ef07-4c00-9d3e-3dcd4f85138d)

# Оновлена сторінка після редагування

![page_after_update](https://github.com/user-attachments/assets/ab0b38a0-a5a2-47dd-88c1-fe1c7de0f76b)

![page_after_update_2](https://github.com/user-attachments/assets/62f0d761-184e-4f4f-915b-b0ebb6f5da5f)

PostgreSQL

![postgres_after_update](https://github.com/user-attachments/assets/359b8045-0004-4f3b-9854-19d04e7b2021)

Як бачимо сутність оновилась.

# Видалення сутності Delete
Тепер видалемо сутність. Наприклад видалимо сутність `Wojciechovsky Alexander`.

Для уього натиснемо кнопку `Видалити`, але перед цим зафіксуємо попередній вигляд

Сайт

![page_after_update_2](https://github.com/user-attachments/assets/39113ab0-cff5-41b1-a147-8dc1ebec2f8e)

PostgreSQL

![postgres_after_update](https://github.com/user-attachments/assets/359b8045-0004-4f3b-9854-19d04e7b2021)

Тепер можемо видаляти

Підтвердити видалення?

![delete_confirmation](https://github.com/user-attachments/assets/c88461cd-a5a9-47ce-9005-604ff3d874ae)

![successful_delete](https://github.com/user-attachments/assets/1f2f37ff-37b2-4edb-a998-ee8287e1adf5)


Пітверджуємо і переглянемо, що відбулося 

Сайт 

![page_after_delete](https://github.com/user-attachments/assets/82542cf4-881d-4bc7-bd94-da8e062d758c)

PostgreSQL

![postgres_after_delete](https://github.com/user-attachments/assets/2c8bd692-c3dd-46f2-87dc-5db3d9d33bd5)

## Додавання нового JWT токену і перевірка роботи:
P.S. Попередня БД була така port=5432 тобто це власноруч створена БД у PostgreSQL

По перше внесемо деякі зміни у коді

![posts_ts](https://github.com/user-attachments/assets/03f7254e-cd3c-461f-87ab-31d8b2c93025)

Потім у Postman зробимо запит.
![new_jwt](https://github.com/user-attachments/assets/45af80bd-ffd5-4018-abf5-2afa84c2d2e4)

Копіюємо наш токен і вставляємо його у файл 

![_env](https://github.com/user-attachments/assets/2e87413e-0aea-4cff-847f-ddee6c91dd79)

Ще змінимо ще один файл

![axios](https://github.com/user-attachments/assets/c9c79aaf-752d-4f78-a816-cbe3a70bfc82)

Тепер запустимо наш проект. Ось наша сторінка

![main_page_new](https://github.com/user-attachments/assets/9f503995-eaaf-41e5-b8c3-7259dac0d1a7)

![main_page_new_1](https://github.com/user-attachments/assets/70b01d76-f152-4997-a3cb-f8c47c8bc6a9)

![main_page_new_2](https://github.com/user-attachments/assets/d8a9345a-4dd9-4527-be2d-01e3379a8133)

# Сторінка Детально

![about_entities_1](https://github.com/user-attachments/assets/5e074cff-2621-4855-b475-545a296f2550)
![about_entities_2](https://github.com/user-attachments/assets/71327bdd-b216-4189-ad1f-5c020c6003a1)

# Редагувати

![update_new_1](https://github.com/user-attachments/assets/6fac3a9f-8e3b-4341-bfef-e0ed41a0a6c4)
![update_new_2](https://github.com/user-attachments/assets/ae30ee26-a1f3-48c5-951d-9ded9990be96)

# Видалити

![delete_new_1](https://github.com/user-attachments/assets/d6f55ff7-bbcf-4aa3-8233-e4e2f17298ee)
![delete_new_2](https://github.com/user-attachments/assets/41e078b1-ed0e-4475-8cc0-9a6fab8ec6ee)

# Створення

![create_new_1](https://github.com/user-attachments/assets/453ea2f5-0bcc-43fa-a5c3-f670dcfd475a)
![create_new_2](https://github.com/user-attachments/assets/cecf8214-4cc2-4c1b-a35d-29427cdae02d)


Як бачимо усі операції CRUD  працюють вдало.

## Загальний висновок

У результаті роботи було успішно реалізовано інтеграцію клієнтської частини з RESTful API. Було повторно використано попередні проєкти з бекенду та фронтенду, налаштовано середовище, оновлено змінні конфігурації у `.env` файлах, а також підключено бібліотеку `axios` для зручної роботи з HTTP-запитами.

На стороні фронтенду були реалізовані функціональні компоненти, які дозволяють виконувати всі базові операції CRUD (створення, читання, оновлення, видалення) над сутностями. Усі ці дії були перевірені як через інтерфейс додатку, так і через Postman для підтвердження коректності обміну даними з API.

Таким чином, інтеграція клієнтської частини з серверною була виконана успішно, що підтверджується стабільною роботою усіх CRUD-операцій та синхронізацією даних між фронтендом і бекендом.
