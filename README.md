# webspark-test-task
Нужно установить и настроить если на сервере нет:
 - Nginx - последняя версия;
 - php-fpm 8.1;
 - Mysql - последняя версия;
 - ssh;
авторизация по паролю запрещена, только по ключам (список ключей в конфигурации Ansible для root);
сменить порт на 1234;
csf;
 - разрешить доступ на сервер по SSH с указанных IP в списках конфигурации;
 - разрешить доступ по протокол HTTP/HTTPS (как дополнение, предложить еще порты если они нужны);
Поднять WP проект:
  В конфигурации Ansible необходимо указать;
  название виртуального хоста для nginx (домен);
  название пользователя;
linux;
  mysql + pass;
* Необходимо установка последней версии https://wordpress.org/download/ .
Будет плюсом:
  Очистка логов;
  мониторинг;
  улучшения по безопасности;
  бекап (на том же сервере каждый день);
  
  
Етапи установки:
1. Клонуємо репозитарій
2. Створюємо локальний ansible vault з стрінгами, в яких шифруємо свої паролі для mysql root, wordpress-user's password
3. Вписуємо свої секрети в файли /group_vars/all.yaml
                                 /roles/mysql/defaults/main.yml
                                 /roles/wordpress/defaults/main.yml
4. При бажанні в файлі /roles/wordpress/defaults/main.yml розкоментовуємо відповідні змінні і вносимо згенеровані значення
|AUTH_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n 
| SECURE_AUTH_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n
| LOGGED_IN_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n
| LOGGED_IN_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n
| NONCE_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n
| AUTH_SALT | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n
| SECURE_AUTH_SALT | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n
| LOGGED_IN_SALT | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n
| NONCE_SALT | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) /n
5. Редагуємо файл inventory під свої потреби
6. Запускаємо плейбук командою ansible-playbook -K -i inventory main.yml --ask-vault-pass

TDL

Потрібно розібратись як коректно обіграти зміну порту ssh з стандартного на інший, щоб щоразу не міняти inventory.  
Стосовно бекапів, очистки логів, моніторингів - то в завданні повинно бути вказано чиї логи чистимо, що бекапимо, що моніторимо і для чого. 
А покращення безпеки додав.
