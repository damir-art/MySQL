# MySQL
Руководство по MySQL
http://mysql.itgid.info/

## Импорт каталога в PHPMyAdmin
* Заходим в PHPMyAdmin
* Вкладка "Базы данных" > Вводим имя > Сравнение: utf8_general_ci > Создать
* Вкладка "Импорт" > Обзор... > Загружаем файл .sql > Вперёд > Зеленые записи (всё в порядке)
* Слева кликаем по загруженной таблице

## Создаём подключение к MySQL через PHP
https://www.w3schools.com/php/php_mysql_select.asp

Создаём файл `config.php` размещаем там код:

    <?php
    /* Подключаемся к базе данных */
    $servername = "localhost"; // имя сервера
    $username = "root";        // логин админа базы
    $password = "";            // пароль админа базы
    $dbname = "c2";

    // Создаем соединение
    $conn = new mysqli($servername, $username, $password, $dbname);

    // Проверяем соединение
    if ($conn->connect_error) {
        die("Ошибка подключения: " . $conn->connect_error);
    }
    echo "<p>Подключение в БД удалось</p>";

    // Создаём SQL-запрос
    $sql = "SELECT id, name, description, cost FROM goods";
    $result = $conn->query($sql);

    if ($result->num_rows > 0) {
        // выходные данные каждой строки
        while($row = $result->fetch_assoc()) {
            echo "<p>" . $row["id"]. " " . $row["name"]. " " . $row["description"] . " " . $row["cost"] . "</p>";
        }
    } else {
        echo "В таблице нет данных";
    }

    // Закрываем соединение
    $conn->close();
