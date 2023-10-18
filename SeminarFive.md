>**Загородных Алексей. Группа №4544**

# **Контейнеризация семинары**

>**Пятый семинар**

* Задание: 1)Cоздать сервис, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД (compose).
           2)Выводы зафиксировать.

Запуск нужных контейнеров
* docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:8.0.31
* docker run --name myphp -d --link some-mysql:db -p 8081:80 phpmyadmin/phpmyadmin

![Снимок экрана от 2023-10-18 19-43-08](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/d2d02e8c-ea35-4c50-bbdc-aef1ca047b8d)

![Снимок экрана от 2023-10-18 19-43-59](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/2c4533ec-aad0-45d5-892f-d3f26621eff9)

Откываем браузер и заходим  на localhost:8081

![Снимок экрана от 2023-10-18 19-53-21](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/dbf3f8ef-9a42-45f3-bb99-32b9f792cd16)

Заполняем поля: пользователь и пароль. Заходим и видим удобный интерфейс для работы

![Снимок экрана от 2023-10-18 19-56-03](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/bc839cfd-8c5f-4840-a61f-eb40649bdea8)

Создаем папку seminar5 и файл в ней docker-compose.yml

* mkdir seminar5
* nano docker-compose.yml

![Снимок экрана от 2023-10-18 20-24-44](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/8a8cd3b5-890c-407b-921e-922d8ce7e3a6)

Прописываем настройки в файле, сохраняем и проверяем

![Снимок экрана от 2023-10-18 20-26-30](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/b03c2da9-8050-4d69-b397-7e1eb6bd99a7)

Собираем и запускаем 

* docker-compose up -d

![Снимок экрана от 2023-10-18 20-33-44](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/eaea968b-6908-4b4c-b3de-e72baa273077)

Проверяем работу

![Снимок экрана от 2023-10-18 20-34-53](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/a3618715-9418-458e-9357-ad1a29ed06e7)

![Снимок экрана от 2023-10-18 20-35-11](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/be52b7b3-8dc1-4612-af50-1237b887cccf)





