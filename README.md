# ansible

Тема: Первые шаги с Ansible

Задача:

1. необходимо использовать модуль yum/apt
2. конфигурационный файлы должны быть взяты из шаблона jinja2 с переменными
3. после установки nginx должен быть в режиме enabled в systemd
4. должен быть использован notify для старта nginx после установки
5. сайт должен слушать на нестандартном порту - 8080, для этого использовать переменные в Ansible


Действаия:

Скачиваем содержимое репозитория и переходим директорию со скаченным

Создаём виртуальную машину:

sudo vagrant up

Для проверки правильности шаблона ansible можно использовать ключ --check

ansible-playbook -i staging/hosts site.yml --check

Вызываем команду ansible-playbook для запуска шаблона site.yml из коренвой директории

ansible-playbook -i staging/hosts site.yml

После выполнения переходим на виртуальную машину и проверяем доступность сайта

vagrant ssh

curl http://127.0.0.1:8080

sudo ss -tnlp