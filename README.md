# Домашнее задание к занятию "10.5 Балансировка нагрузки. HAProxy/Nginx."

Домашнее задание выполните в Google Docs и отправьте в личном кабинете на проверку ссылку на ваш документ.

Название файла должно содержать номер лекции и фамилию студента. Пример названия: "10.5 Балансировка нагрузки. HAProxy/Nginx - Александр Александров".

Перед тем как выслать ссылку, убедитесь, что ее содержимое не является приватным (открыто на просмотр всем, у кого есть ссылка). Если необходимо прикрепить дополнительные ссылки, просто добавьте их в свой Google Docs.

Любые вопросы по решению задач задавайте в чате учебной группы.

---

### Задание 1.

Что такое балансировка нагрузки и зачем она нужна?
Распределение нагрузки на обработку запросов по пулу серверов  для достижения отказоустойчивости и рационального распределения ресурсов (повыщения быстродействия) Также возможны стратегии распределения в зависимости от (географии пользователей, загруженности серверов, ввода новых релизов и тд)

*Приведите ответ в свободной форме.*

---

### Задание 2.

Чем отличаются между собой алгоритмы балансировки round robin и weighted round robin? В каких случаях каждый из них лучше применять? 
RR --обращение идет по кругу (циклу)
при добавлении весов --обращение также по кругу (циклу), только где вес больше то необходимо набрать N кол-во обращений чтобы цикл сдвинулся. Логично использовать когда в кластере разные сервера по производительности. 

*Приведите ответ в свободной форме.*

---

### Задание 3.

Установите и запустите haproxy.

*Приведите скриншот systemctl status haproxy, где будет видно, что haproxy запущен*

![alt text](https://github.com/vasev85/HAproxy/blob/main/ex1.png?raw=true) 
---

### Задание 4.

Установите и запустите nginx.

*Приведите скриншот systemctl status nginx, где будет видно, что nginx запущен*

---

### Задание 5.

Настройте nginx на виртуальной машине таким образом, чтобы при запросе:

`curl http://localhost:8088/ping`

он возвращал в ответе строчку: 

"nginx is configured correctly"

*Приведите скриншот получившейся конфигурации*

---

## Дополнительные задания (со звездочкой*)

Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.

---

### Задание 6*.

Настройте haproxy таким образом, чтобы при ответе на запрос:

`curl http://localhost:8080/`

он проксировал его в nginx на порту 8088, который был настроен в задании 5 и возвращал от него ответ: 

"nginx is configured correctly". 

*Приведите скриншот получившейся конфигурации*
