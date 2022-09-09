Wordpress Role
=========

Role for deploying wordpress application in existing infrastructure.

Requirements
------------

You should have deployed web server (currently supports only Nginx) on host with support PHP FPM and also you need to have MySQL server.

Role Variables
--------------

| Name | Description | Default | Required |
|------|-------------|---------|:--------:|
| AUTH_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `random` | no |
| SECURE_AUTH_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `random` | no |
| LOGGED_IN_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `"eu-central-1"` | no |
| LOGGED_IN_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `"eu-central-1"` | no |
| NONCE_KEY | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `"eu-central-1"` | no |
| AUTH_SALT | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `"eu-central-1"` | no |
| SECURE_AUTH_SALT | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `"eu-central-1"` | no |
| LOGGED_IN_SALT | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `"eu-central-1"` | no |
| NONCE_SALT | WordPress security keys. Can be generated [here](https://api.wordpress.org/secret-key/1.1/salt/) | `"eu-central-1"` | no |
| domain_name | Domain name which will be used in site configuration | `wp.com` | no |
| app_name | Name of wordpress application which will be used in folders naming | `wordpress` | no |
| php_fpm_sock | Path to PHP FPM socket | `/run/php/php-fpm.sock` | no |
| sites_path | Folder where sites files stored | `/var/www/http_host` | no |
| db_name | Name of database where wordpress data stored | `wordpress` | no |
| db_host | MySQL host where wordpress db located | `localhost` | no |
| db_username | Username for communication with MySQL DB | `wordpressuser` | no |
| db_password | Password for communication with MySQL DB | `wordpresspass` | no |

Dependencies
------------

PHP, Webserver and Database can be installed using roles in same Ansible Galaxy collection.

Example Playbook
----------------

Example of usage can be found in test folders inside role and inside collection.

License
-------

BSD
