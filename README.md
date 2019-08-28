# MySQL
Руководство по MySQL

## Импорт каталога в PHPMyAdmin
* Заходим в PHPMyAdmin
* Вкладка "Базы данных" > Вводим имя > Сравнение: utf8_general_ci > Создать
* Вкладка "Импорт" > Обзор... > Загружаем файл .sql > Вперёд > Зеленые записи (всё в порядке)
* Слева кликаем по загруженной таблице

### Содержание
* [Подключение к базе данных PHP](https://damir-art.github.io/mysql/mysqli_connect/)

## Добавление пользователя в БД (логин, пароль)
Добавлем пользователя БД, затем по логину и паролю он может попасть в личный кабинет.
* Создаём таблицу `users`
* В PHPMyAdmin слева кликаем по БД
* Под именем БД кликаем по ссылке "Новая"
* Имя таблицы `users`, далее создаём поля таблицы:
    * id (автоинкремент, primary)
    * login (varchar, 50)
    * email (varchar, 50)
    * pass (varchar, 50) сохранить
    * Добавляем еще одно поле "Добавить 1 поле после pass вперед"
    * hash (varchar, 50) сохранить, вкладка "Обзор"
* Заполняем поля таблицы `users`
    * Жмём по вкладке "Вставить"
    * login (ivan)
    * email (ivan@ivan)
    * pass (md5, ivan123) вперёд, вкладка "Обзор"

Файл `login.php`, код обработки формы, сама форма
    
    код

### Как удалить таблицу
* В PHPMyAdmin слева выбираем таблицу
* Жмём по вкладке "Операции"
* Снизу жмем по "Удалить таблицу"

### Разное
* MD5 - функция хэша которая генерирует 32-х символьную строку из любого пароля (16-тиричная система счисления)

### Ссылки
https://www.youtube.com/channel/UCvqXOuAHAc76rtZVVE4qfJw<br />
http://mysql.itgid.info/<br />
https://shultais.education/<br />
