# Подключение к базе данных
## Создаём подключение к MySQL через PHP
https://www.w3schools.com/php/php_mysql_select.asp

Создаём файл `config.php` размещаем там код:

    <?php
    /*
    Файл настроек базы данных.
    Подключаемся к базе, вместо переменных создаём константы.
    Константы доступны везде, где подключен файл config.php
    \*/
    define('SERVERNAME', 'localhost'); // имя сервера
    define('USERNAME', 'root');        // логин пользователя базы
    define('PASSWORD', '');            // пароль пользователя базы
    define('DBNAME', 'c2');            // имя базы

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
