## Описание решения
Задание было выполнено с использованием __Ansible roles__
Для создание структуры папок для роли nginx выполнена команда:
```sh
```
На одном уровне с папкой roles была созданы папки inventories и playbooks
В roles/nginx/tasks/main.yml описаны задачи:
- установки epel-release репозитория
- net-tools для проверки порта через netstat
- nginx сервера
- копирования index.html
- копирования конфигурации default.conf  с кастомным портом
В roles/nginx/handlers/main.yml описаны обработчики: 
- старта сервиса nginx
- рестарта сервиса nginx
В roles/nginx/templates/ лежат шаблоны: 
- index.html.j2 - стартовой стратицы сервера
- default.conf.j2 - конфигурационного файла
В roles/nginx/vars/main.yml задекларированы переменные: 
- репозитория
- кастомного порта nginx

Проверка.
Все действия выполняются на единственной машине, которая поднимаетася через Vagrant 
1. Clone repo
2. vagrant up
3. Запуск playbook: ansible-playbook -i inventories/staging/ playbooks/nginx_run_role.yml
4. Проверить касмтомный порт nginx: 
