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

