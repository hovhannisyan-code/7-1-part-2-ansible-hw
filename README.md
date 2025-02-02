Домашнее задание к занятию "Ansible. Часть 2" - Оганесян Гор

### Задание 1

**Выполните действия, приложите файлы с плейбуками и вывод выполнения.**

Напишите три плейбука. При написании рекомендуем использовать текстовый редактор с подсветкой синтаксиса YAML.

Плейбуки должны: 

1. Скачать какой-либо архив, создать папку для распаковки и распаковать скаченный архив. Например, можете использовать [официальный сайт](https://kafka.apache.org/downloads) и зеркало Apache Kafka. При этом можно скачать как исходный код, так и бинарные файлы, запакованные в архив — в нашем задании не принципиально.
2. Установить пакет tuned из стандартного репозитория вашей ОС. Запустить его, как демон — конфигурационный файл systemd появится автоматически при установке. Добавить tuned в автозагрузку.
3. Изменить приветствие системы (motd) при входе на любое другое. Пожалуйста, в этом задании используйте переменную для задания приветствия. Переменную можно задавать любым удобным способом.



![screen_change_motd](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/img/screenshot_0.png)
[Download package](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/download_package.yml)

![res-install-motd](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/img/screenshot_1.png)
[Install tuned](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/install_tuned.yml)

![change_motd](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/img/screenshot_2.png)
![change_motd_screen](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/img/screenshot_3.png)
[Change motd](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/change_motd.yml)


### Задание 2

**Выполните действия, приложите файлы с модифицированным плейбуком и вывод выполнения.** 

Модифицируйте плейбук из пункта 3, задания 1. В качестве приветствия он должен установить IP-адрес и hostname управляемого хоста, пожелание хорошего дня системному администратору. 

![change_motd_2](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/img/screenshot_4.png)
![change_motd_2_screen](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/img/screenshot_5.png)
[Change motd 2](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/change_motd-2.yml)



### Задание 3

**Выполните действия, приложите архив с ролью и вывод выполнения.**

Ознакомьтесь со статьёй [«Ansible - это вам не bash»](https://habr.com/ru/post/494738/), сделайте соответствующие выводы и не используйте модули **shell** или **command** при выполнении задания.

Создайте плейбук, который будет включать в себя одну, созданную вами роль. Роль должна:

1. Установить веб-сервер Apache на управляемые хосты.
2. Сконфигурировать файл index.html c выводом характеристик каждого компьютера как веб-страницу по умолчанию для Apache. Необходимо включить CPU, RAM, величину первого HDD, IP-адрес.
Используйте [Ansible facts](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_vars_facts.html) и [jinja2-template](https://linuxways.net/centos/how-to-use-the-jinja2-template-in-ansible/). Необходимо реализовать handler: перезапуск Apache только в случае изменения файла конфигурации Apache.
4. Открыть порт 80, если необходимо, запустить сервер и добавить его в автозагрузку.
5. Сделать проверку доступности веб-сайта (ответ 200, модуль uri).

В качестве решения:
- предоставьте плейбук, использующий роль;
- разместите архив созданной роли у себя на Google диске и приложите ссылку на роль в своём решении;
- предоставьте скриншоты выполнения плейбука;
- предоставьте скриншот браузера, отображающего сконфигурированный index.html в качестве сайта.

![Show terminal](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/img/screenshot_6.png)
![Show page](https://github.com/hovhannisyan-code/7-1-part-2-ansible-hw/blob/master/img/screenshot_7.png)