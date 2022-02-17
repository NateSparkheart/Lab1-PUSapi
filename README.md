Технологии разработки программного обеспечения

Лабораторная работа №1

Разработка микросервиса (REST API) на Springboot, имеющего определенную базу данных 

Выполнил: студент группы МБД 2131 Савицкий В.Д.

Цель работы работы: Познакомиться с проектированием многослойной архитектуры Web-API (веб-приложений и микро-сервисов)

Для запуска приложения необходимо:

1. Клонировать код проекта с репозитория:  git clone https://github.com/NateSparkheart/PUSapi
2. Запустить базу данных как докер-контейнер: docker run -e POSTGRES_PASSWORD=root -p 5432:5432 postgres
3. Заполнить базу данных данных с помощью файлов, находящихся в директории PUSapi/Исходный код/Ресурсы/
4. Собрать с помощью команды docker build . -t myapi:latest докер-образ приложения (докер-файл находится в директории PUSapi/Исходный код/Dockerfile/)
5. Запустить докер-контейнер с приложением  docker run -p 8080:8080 myapi:latest

Чтобы собрать приложение в Maven из командной строки необходимо использовать команду mvnw package

Запросы к API (к endpoint-ам приложения):
Получить имя хоста:
Запрос типа GET http://localhost:8080/api/v1/status

Получить всех записи из базы данных:
Запрос типа GET http://localhost:8080/api/v1/product

Получить запись из базы данных по id (4):
Запрос типа GET http://localhost:8080/api/v1/product/4

Вненсти в базу данных новую аппаратуру:
Запрос типа POST http://localhost:8080/api/v1/product/



Удаление записи из базы данных по id:
Тип запроса DELETE http://localhost:8080/api/v1/products/5
