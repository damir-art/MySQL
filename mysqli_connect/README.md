# Подключение к базе данных
## Создаём подключение к MySQL через PHP
https://www.w3schools.com/php/php_mysql_select.asp

Создаём файл `config.php` размещаем там код:

    <?php
    /*
        Файл настроек базы данных.
        Подключаемся к базе, вместо переменных создаём константы.
        Константы доступны везде, где подключен файл config.php
    */
    define('SERVERNAME', 'localhost'); // имя сервера
    define('USERNAME', 'root');        // логин пользователя базы
    define('PASSWORD', '');            // пароль пользователя базы
    define('DBNAME', 'c2');            // имя базы

    require_once 'config.php';

    // Создаем соединение
    // $conn - ссылка на соединение с базой данных (ссылка на ресурс)
    $conn = mysqli_connect(SERVERNAME, USERNAME, PASSWORD, DBNAME);

    mysqli_set_charset($conn, 'utf8'); // Принудительно  ставим кодировку если возникают крякозябры

    if (!$conn) {
        die('Ошибка подключения: ' . mysqli_connect_error());
    } else {
        echo '<h3>Подключились к базе!</h3>';
    }

    $sql = 'SELECT name, description FROM goods';
    $result = mysqli_query($conn, $sql);

    // $a = array();

    if (mysqli_num_rows($result) > 0) {
        // row - это строка таблицы
        while($row = mysqli_fetch_assoc($result)) {
            echo $row['name'] . ' ' . $row['description'] . '<br />';
            // $a[] = $row;
        }
    } else {
        echo "В таблице нет данных!";
    }

    // pre_var($a);

    mysqli_close($conn);
