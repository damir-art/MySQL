# Установка MySQL сервера и клиента HeidiSQL

## MySQL Community Server 5.7
### Загрузка инсталлера
* mysql.com > downloads > community
* MySQL Community Server (https://dev.mysql.com/downloads/mysql/)
* MySQL Community Server 5.7 > Go to Download Page > Качаем то что меньше весит
* Download > No thanks, just start my download > Начинается загрузка

### Установка
* Да (2 раза), Нет апгрейду.
* Да (лицензия) > Некст
* Server only (Некст)
* (Предлагают установить доп компоненты С++, если их не в компе) выбираем MySQL > Execute
* Execute > Качаем MySQL > Next (4 раза)
* Вводим пароль > Next (3 раза) убери галку "запускать вместе с виндой"
* Execute > Finish > Next > Finish

## HeidiSQL 10.2
### Установка
* heidisql.com > Downloads > Installer (загрузится установщик)
* Да, Принимаю (Далее 3 раза), Установить

### Использование
* Подключаемся к серверу: Создать > Вводим пароль
* Переименовываем сеанс (прав кн) > Сохранить > Открыть
* **Создём базу данных**
    * Правая кн по сайдбару > Создать > База данных (имя, utf8_general_ci) > OK
* **Выполняем SQL-файл, содержащий запросы**
    * Файл > Выполнить SQL-файл > Найти, Открыть > Обновить прогу
* **Выполняем SQL-запрос**
    * Выбираем таблицу > Вкладка "Запрос" > Вводим запрос > Синий треугольник (F9)

## Команды консоли к БД

    net stop mysql57
    net start mysql57
