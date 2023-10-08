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
