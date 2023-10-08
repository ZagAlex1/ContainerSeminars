>**Загородных Алексей. Группа №4544**

# **Контейнеризация семинары**

>**Третий семинар**

* Задание:
1. Подготовить пакеты и установить Docker.
2. Запустить docker и попрактиковаться в нем.

Подготовка к установке и установка docker

* sudo apt update
* sudo apt install apt-transport-https ca-certificates curl software-properties-common
* curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
* echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
* | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
* sudo apt update
* sudo apt install docker-ce
* sudo usermod -aG docker $USER
* newgrp docker
* docker --version

![Снимок экрана от 2023-10-08 19-22-54](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/457bd778-6d40-418c-9a51-6aac0263de4a)

Проверка работы 

* docker run docker/whalesay cowsay Hello, Docker!
* docker run docker/whalesay cowsay -f elephant "Hello, Docker!"
* docker run docker/whalesay cowsay -f tux "Hello, Docker!"
* docker run docker/whalesay cowsay -f dragon "Hello, Docker!"

![Снимок экрана от 2023-10-08 19-34-26](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/3dcdcb60-35c2-4ada-8dc6-5844d43a6fcd)

Тренировка в удалении 

![Снимок экрана от 2023-10-08 19-57-54](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/6248bda9-2ef2-4c23-9b09-b80d5942545a)

* docker rmi 2657a4a0a6d5
* docker rmi 692eb4a905c0 3e4394f6b72f
* docker rmi 692eb4a905c0 6b362a9f73eb --force
* docker rm $(docker ps -aq) --force

![Снимок экрана от 2023-10-08 20-06-09](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/39dff869-b8ea-48b9-a88e-413f5d29becb)

Работа с контейнером

* docker run -it -h GB --name gb-test ubuntu:22.10
* ls -l
* ps aux

![Снимок экрана от 2023-10-08 20-15-53](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/0c02bd42-cccd-46b5-aae2-b85f410fee27)

* mkdir /example
* touch /example/passwords.txt
* echo "123test" >> /example/passwords.txt

![Снимок экрана от 2023-10-08 20-19-28](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/b277b0d5-4046-4084-95e3-3cdc139a7f25)

* docker stop gb-test
* docker start gb-test
* docker exec -it gb-test bash

Настройка двусторонней связи между контейнером и папкой хостовой системы

* sudo mkdir /test
* sudo mkdir /test/folder
* docker run -it -h GB --name gb-test-2 -v /test/folder:/otherway ubuntu:22.10
* cd otherway/
* touch passwords.txt
* echo "123test" >> passwords.txt

![Снимок экрана от 2023-10-08 20-48-11](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/68be1c7f-4e28-41fb-ad8e-05018c55ea89)

* exit
* cat /test/folder/passwords.txt
* sudo su
* sudo echo "main system" >> passwords.txt

![Снимок экрана от 2023-10-08 20-59-37](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/eea71c46-3241-4789-bf3d-95d165ef1328)

* docker start gb-test-2
* docker exec -it gb-test-2 bash
* cat otherway/passwords.txt

![Снимок экрана от 2023-10-08 21-06-13](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/f8011cdc-1c30-459d-8be3-664dadec4942)




