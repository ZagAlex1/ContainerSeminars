>**Загородных Алексей. Группа №4544**

# **Контейнеризация семинары**

>**Первый семинар**

* Задание: необходимо продемонстрировать изоляцию одного и того же приложения (как решено на семинаре - командного 
  интерпретатора) в различных пространствах имен.

Создал папку containerOne, перешел в нее и скопировал туда bash из корня

* mkdir containerOne
* cd containerOne/
* mkdir bin
* cd bin/
* cp /bin/bash ~/containerOne/bin/
  
![Снимок экрана от 2023-10-02 20-19-18](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/3261147a-efbc-49a2-b31b-e7d6426aaa3a)

Использовал команду ldd /bin/bash, что-бы посмотреть нужные зависимости.

![Снимок экрана от 2023-10-02 20-30-17](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/defaaf07-4019-40be-9e95-371c223bb156)

Создаю папки для библиотек, копирую их туда и пробую поменять корневой каталог.
* mkdir ~/containerOne/lib
* mkdir ~/containerOne/lib64
* cp /lib/x86_64-linux-gnu/libtinfo.so.6 ~/containerOne/lib
* cp /lib/x86_64-linux-gnu/libc.so.6 ~/containerOne/lib
* cp /lib64/ld-linux-x86-64.so.2 ~/containerOne/lib64/
* cp /lib/x86_64-linux-gnu/libc.so ~/containerOne/lib
* sudo chroot ~/containerOne/

![Снимок экрана от 2023-10-02 20-44-22](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/129a6c88-71ec-4ad9-9b6f-2653237cc9d4)

Создал изолированное сетевое окружение и подключился к нему(изолировался по сети)
* sudo ip netns add testns
* sudo ip netns exec testns bash

![Снимок экрана от 2023-10-02 21-11-19](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/fa1fc36c-49f6-4ca2-beb7-885c9cbd0719)

Изоляция с дополнительными параметрами

* sudo unshare --net --pid --fork --mount-proc /bin/bash

![Снимок экрана от 2023-10-02 21-20-58](https://github.com/ZagAlex1/ContainerSeminars/assets/93830341/6779b09d-6cd6-4568-af0c-b854bdc39609)











