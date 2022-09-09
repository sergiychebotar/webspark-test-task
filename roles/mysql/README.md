MySQL Role
=========

Role for deploying MySQL server, database and user for communication with DB server.

Role Variables
--------------

| Name | Description | Default | Required |
|------|-------------|---------|:--------:|
| root_password | Password for root user in DB | `root` | no |
| db_name | Name of database which will be created | `db` | no |
| user_name | Username for database admin | `user` | no |
| user_pass | Password for database admin | `pass` | no |

Example Playbook
----------------

Example of usage can be found in test folders inside role and inside collection.

License
-------

BSD
