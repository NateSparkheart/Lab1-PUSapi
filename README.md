Технологии разработки программного обеспечения

Лабораторная работа №1

Разработка микросервиса (REST API) на Springboot, имеющего определенную базу данных 

Выполнил: студент группы МБД 2131 Савицкий В.Д.

Цель работы работы: Познакомиться с проектированием многослойной архитектуры Web-API (веб-приложений и микро-сервисов)

Для запуска приложения необходимо:

1. Клонировать код проекта с репозитория:  git clone https://github.com/NateSparkheart/PUSapi
2. Запустить базу данных как докер-контейнер: 

   docker run -e POSTGRES_PASSWORD=root -p 5432:5432 postgres
3. Заполнить базу данных данных с помощью файлов, находящихся в директории PUSapi/Исходный код/Ресурсы/
4. Собрать с помощью команды 

   docker build . -t myapi:latest 
   
   докер-образ приложения (докер-файл находится в директории PUSapi/Исходный код/Dockerfile/)
5. Запустить докер-контейнер с приложением: 

   docker run -p 8080:8080 myapi:latest

Чтобы собрать приложение в Maven из командной строки необходимо использовать команду:
   mvnw package

Запросы к API (к endpoint-ам приложения):
Получить имя хоста:
Запрос типа GET 

http://localhost:8080/api/v1/status

Получить всех записи из базы данных:
Запрос типа GET

http://localhost:8080/api/v1/product

Получить запись из базы данных по id (4):
Запрос типа GET

http://localhost:8080/api/v1/product/4

Вненсти в базу данных новую аппаратуру:
Запрос типа POST 

http://localhost:8080/api/v1/product/

Тело запроса(пример):

{

	"name": "Мультиплексор",
	
	"brand": "Стрела",
	
	"price": 150000,
	
	"quantity": 1	
}

Удаление записи из базы данных по id:
Тип запроса DELETE 

http://localhost:8080/api/v1/product/5

Лабораторная работа №3

CI/CD и деплой приложения в Heroku

Выполнил: студент группы МБД 2131 Савицкий В.Д.

Цель работы работы: Знакомство с CI/CD и его реализацией на примере Travis CI и Heroku.

Badge: 

[![Build Status](https://app.travis-ci.com/NateSparkheart/simpleapi.svg?branch=master)](https://app.travis-ci.com/NateSparkheart/simpleapi)

Ошибка, мешающая деплою приложения

![alt text](https://github.com/NateSparkheart/simpleapi/blob/master/%D0%9E%D1%88%D0%B8%D0%B1%D0%BA%D0%B0,%20%D0%BC%D0%B5%D1%88%D0%B0%D1%8E%D1%89%D0%B0%D1%8F%20%D0%B4%D0%B5%D0%BF%D0%BB%D0%BE%D1%8E.png?raw=true)

Cсылка на приложение в Heroku: https://simpleapi-pus.herokuapp.com/
