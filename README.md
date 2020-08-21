# Test_task_exmo
Test_task

# Данные для mysql
db_name: exmo_test
login: exmo_admin
password: admin

# Перейдем в созданный проект и убедимся, что все работает, запустив команду php artisan serve
php artisan serve

# composer update

# Создадим БД - заходим под root правами так как нужно создавать пользователей
mysql -u root -p 
# Помимо БД создаем и пользователя тоже
> CREATE DATABASE `exmo_test` CHARACTER SET utf8 COLLATE utf8_general_ci;
> CREATE USER 'exmo_admin'@'localhost' IDENTIFIED BY 'admin';
> GRANT ALL PRIVILEGES ON exmo_test.* TO 'exmo_admin'@'localhost';
> exit

# Создадим необходимые Таблицы и Модели
# Во первых создадим таблицу миграций
php artisan migrate:install

php artisan make:model Category -mc