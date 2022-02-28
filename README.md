# Homework 8.5

Прогон теста ролей с помощью molecule:  
[kibana_role:1.1.0](https://github.com/Evgeniy-Nikolskiy/kibana_role/releases/tag/1.1.0)  
[filebeat_role:1.1.0](https://github.com/Evgeniy-Nikolskiy/filebeat_role/releases/tag/1.1.0)

В ходе тестирования столкнулся с проблемой получения данных для ОС Centos 8. Решил с помощью сборки нового образа и 
добавления туда необходимого фикса:

````
FROM docker.io/pycontribs/centos:8

RUN cd /etc/yum.repos.d/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
RUN yum update -y
````
Прогон теста ролей с помощью tox:  
[kibana_role:1.2.0](https://github.com/Evgeniy-Nikolskiy/kibana_role/releases/tag/1.2.0)  
[filebeat_role:1.2.0](https://github.com/Evgeniy-Nikolskiy/filebeat_role/releases/tag/1.2.0)  

