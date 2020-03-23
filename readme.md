## Описание решения
Задание было выполнено с использованием __Ansible roles__
Для создание структуры папок для роли nginx выполнена команда:
```sh
```
На одном уровне с папкой _roles_ была созданы папки _inventories_ и _playbooks_.
В _roles/nginx/tasks/main.yml_ описаны задачи:  
- установки epel-release репозитория
- установки net-tools для проверки порта через netstat
- установки nginx сервера
- копирования index.html
- копирования конфигурации default.conf  с кастомным портом  
  
В _roles/nginx/handlers/main.yml_ описаны обработчики: 
- старта сервиса nginx
- рестарта сервиса nginx
  
В _roles/nginx/templates/_ лежат шаблоны:   
- index.html.j2 - стартовой стратицы сервера
- default.conf.j2 - конфигурационного файла  
  
В _roles/nginx/vars/main.yml_ задекларированы переменные: 
- репозитория
- кастомного порта nginx

Проверка.
Все действия выполняются на единственной машине, которая поднимаетася через Vagrant 
1. Clone this repo
2. vagrant up
3. Запуск playbook: ansible-playbook -i inventories/staging/ playbooks/nginx_run_role.yml
4. Проверить касмтомный порт nginx:  netstat -an | grep 8080

