# 2023_2024-introduction_to_distributed_technologies-K4112c-maksimova_d_d
University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2023/2024
Group: K4112c
Author: Maksimova Daria Dmitrievna
Lab: Lab1
Date of create: 08.11.2024
Date of finished: 08.11.2024

# Лабораторная работа №1 "Установка Docker и Minikube, мой первый манифест."
## Описание
Это первая лабораторная работа в которой вы сможете протестировать Docker, установить Minikube и развернуть свой первый "под".

## Цель работы
Ознакомиться с инструментами Minikube и Docker, развернуть свой первый "под".

## Теория
### Docker 
[What is Docker? | Docker Docs](https://docs.docker.com/get-started/docker-overview/)

Docker позволяет упаковывать и запускать приложение в изолированной среде, называемой контейнером.
Изоляция и безопасность позволяют запускать множество контейнеров одновременно на заданном хосте. 
Контейнеры имеют небольшой вес и содержат всё необходимое для запуска приложения. Docker предоставляет инструменты и платформу для управления жизненным циклом контейнеров

#### Объекты Docker
- Images — это шаблон(только для чтения) с инструкциями по созданию Docker контейнера, который объединяет приложение с его средой выполнения, библиотеками и зависимостями и представляет собой исходный код контейнера. 
Контейнеры могут быть развернуты из определенного образа на многих платформах.

Чтобы создать собственный образ, необходимо создать файл Dockerfile с простым синтаксисом для определения шагов, 
необходимых для создания и запуска образа. 
Каждая инструкция в файле Dockerfile создает слой в образе. 
Когда Вы изменяете Dockerfile и перестраиваете образ, то только измененные слои перестраиваются. 
Это то, что делает шаблоны такими легкими, маленькими, и быстрыми, по сравнению с другими технологиями виртуализации. 
- Контейнер — это экземпляр образа, который можно запустить (процесс, выполняемый на главном компьютере, который изолирован от всех других процессов, выполняемых на этом компьютере) 

- Микросервисы - легкие приложения со специфическими зависимостями, библиотеками и требованиями к среде. Чтобы приложение имело все необходимое для успешной работы, оно упаковывается вместе со своими зависимостями.

Контейнеры инкапсулируют микросервисы и их зависимости, но не запускают их напрямую. Контейнеры запускают образы контейнеров.
Вы можете создавать, запускать, останавливать, перемещать или удалять контейнер с помощью Docker API или интерфейса командной строки.
Контейнер определяется его шаблоном, а также любыми параметрами конфигурации, которые вы предоставите ему при создании или запуске. 
При удалении контейнера любые изменения в его состояния, которые не хранятся в постоянном хранилище исчезают.

### Kubernetes 
[Overview | Kubernetes]
Kubernetes — это переносимая, расширяемая платформа с открытым исходным кодом для управления контейнерными рабочими нагрузками и службами. 

### Minikub
[Документация по Minikub](https://minikube.sigs.k8s.io/docs/)

Minikube — это локальный Kubernetes, ориентированный на то, чтобы упростить его изучение и разработку для Kubernetes.

## Ход работы
1. Установка Docker и Minikub на рабочий компьютер

2. Развертывание minikube cluster
![Развертывание minikube cluster](https://github.com/user-attachments/assets/52dd0000-6b62-483c-a13a-5319d940a0ca)

3. Создание контейнера
- скачиваем образ
![скачиваем образ](https://github.com/user-attachments/assets/6f75f257-1f36-4022-9a3b-f29b0c4ae468)
- создаем контейнер на основе образа
![Создаем контейнер](https://github.com/user-attachments/assets/3b2951cf-4ff9-4958-a81b-53a35deef58a)

- проверяем создание контейнера  
![Проверяем, что появился контейнер](https://github.com/user-attachments/assets/9cdcb0b0-6337-47d9-b81d-dfd29eef91ec)

4. Создание сервиса
- создание манифеста YAML

- применения манифеста

- проверка появления Pod

- создаем сервис для доступа к Pod

- перенаправляем трафик на контейнер

- страница авторизации Vault http://localhost:8200.

- поиск токена для авторизации (hvs.IOVMRKyI7ax1O0KdDB52RYzX)

- останавливаем minikube cluster командой minikube stop.

