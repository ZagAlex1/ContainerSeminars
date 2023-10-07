>**Загородных Алексей. Группа №4544**

# **Контейнеризация семинары**

>**Второй семинар**

* Задание:
1) запустить контейнер с ubuntu, используя механизм LXC
2) ограничить контейнер 256 Мб ОЗУ и проверить, что ограничение работает

Установка LXC
* apt-get install lxc debootstrap bridge-utils lxc-templates
* snap install lxd(у меня так получилось). apt-get install lxd-installer(не нашел)
* lxd init
* lxc storage list

![Снимок экрана от 2023-10-07 22-10-29](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/0ffdd034-4075-4f88-b308-5d0378323c2d)

Создание контейнера и проверка памяти
* sudo lxc-create -n test123 -t ubuntu
* sudo lxc-start -n test123
* sudo lxc-ls -f
* sudo lxc-attach -n test123
* free -m
* exit
* sudo lxc-stop -n test123

![Снимок экрана от 2023-10-07 23-04-30](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/92475111-ad6a-4a9c-aa25-2bd0698d30f9)

Ограничение памяти и проверка
* sudo nano /var/lib/lxc/test123/config

![Снимок экрана от 2023-10-07 23-15-34](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/b159b79f-583c-4363-8076-8a4b178138fb)

* sudo lxc-start -n test123
* sudo lxc-attach -n test123
* free -m

![Снимок экрана от 2023-10-07 23-17-14](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/e01c63f7-639a-47d1-9b9d-fb9ceff80fba)


