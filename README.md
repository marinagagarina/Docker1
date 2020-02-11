## Домашнее задание к занятию «3.1. Docker»

### Задача №1 - PostgreSQL

Необходимо подготовить приложение к тестированию на 
СУБД PostgreSQL, используя образ 12.0-alpine.

Нужно взять собранный jar-файл db-api.jar, аналогично 
примеру на лекции, положить рядом файл application.properties, 
но в строке: jdbc:mysql://... поменять mysql на postgresql.

Нужно дописать остальные настройки (хост, порт, БД, имя пользователя и пароль).

Нужно подготовить файл docker-compose.yml, в котором прописать 
настройки для запуска контейнера PostgreSQL. 
Всю информацию о его (контейнера) запуске можно найти на официальной 
странице образа на Docker Hub.

Запустить сначала docker-compose up и только после того, 
как БД запуститься, запустить целевое приложение: java -jar db-api.jar
 (если нужно поменять порт запуска, по умолчанию он 9999, 
 то добавить в файл application.properties строку server.port=<нужный номер порта>).
 
 
 Приложение запускается и на GET http://localhost:9999/api/cards выдает JSON с картами:
 
 ````
[ 
   { 
      "id":1,
      "name":"Альфа-Карта Premium",
      "description":"Альфа-Карта вернёт ваши деньги",
      "imageUrl":"/alfa-card-premium.png"
   },
   { 
      "id":2,
      "name":"Alfa Travel Premium",
      "description":"Самая выгодная карта для путешествий",
      "imageUrl":"/alfa-card-travel.png"
   },
   { 
      "id":3,
      "name":"CashBack Premium",
      "description":"Заправь свою карту. Кэшбэк на АЗС, в кафе и ресторанах",
      "imageUrl":"/alfa-card-cashback.png"
   }
]
````

В результате выполнения этой задачи в репозитории находятся следующие файлы:

* db-api.jar
* application.properties
* docker-compose.yml