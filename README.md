## ﻿Домашнее задание по теме " Docker: основы работы с контейнеризацией"

  1. #### Создан образ nginx на базе alpine.
Задание выполнялось на VM Fedora Linux Release 41 и nginx-1.27.3.
Приложен Dockerfile и начальная страница nginx. Ход выполнения отражен на скриншотах. 
Собранный образ запушен в docker hub:

https://hub.docker.com/r/alexandervakulenko/nginxtest
     
  2. #### Теоретические вопросы:
    
Docker-образ — это шаблон, из которого создаются контейнеры. Образ содержит всё необходимое для запуска контейнеризированного приложения на любой *nix клиентской системе. Образы Docker – это шаблоны, доступные только для чтения и содержащие инструкции по созданию контейнера.

Docker-контейнер — это запущенный и изолированный образ с дополнительным верхним write/read-слоем, хранящим временные данные, которые уничтожаются после удаления контейнера. Контейнерам можно назначать лимиты ресурсов и строить между ними сети.

Образы могут существовать без контейнеров, тогда как для существования контейнеров необходимо запустить образ.

Если необходимо изменить образ, необходимо изменить файл, в то время как контейнер можно изменить во время его выполнения.

Образ изпользуется для хранения сведений о конфигурации приложения в виде шаблона, а контейнер для запуска приложения. 

Образ содержит приложение со всем его окружением, но не содержит данных и не "знает" о взаимодействии, в частности, порт взаимодействия.

Контейнеры запускают образ с указанием параметров связи с "внешним" миром, в частности, монтируют директории с данными, дают TCP-порты для взаимодействия.


Можно ли в контейнере собрать ядро?
  Собрать можно, но если не использовать монтирование данных на внешнем мире, то после перезапуска контейнера все сотрется
