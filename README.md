# Домашнее задание к занятию "`Кеширование Redis/memcached`"
# Халатов Александр

### Задание 1. Кеширование
Приведите примеры проблем, которые может решить кеширование.
Приведите ответ в свободной форме.

### *Ответ:*

- Уменьшение времени отклика
- Повышение производительности
- Снижение нагрузки на основной сервер в пиках запросов
- Уменьшение нагрузки на основную базу данных
- Прогнозируемая производительность

---

### Задание 2. Memcached

Установите и запустите memcached.

*Приведите скриншот systemctl status memcached, где будет видно, что memcached запущен.*

### *Ответ:*
Установка memcached
```
sudo apt-get install memcached
```
Проверка статуса memcached
```
sudo systemctl status memcache
```
![1](https://github.com/IMiroxxI/redis-memcached/blob/main/1/1.jpg)

---

### Задание 3. Удаление по TTL в Memcached

Запишите в memcached несколько ключей с любыми именами и значениями, для которых выставлен TTL 5. 

*Приведите скриншот, на котором видно, что спустя 5 секунд ключи удалились из базы.*

### *Ответ:*
### Ключ k3 задан с TTL=5

```
telnet localhost 11211

version
get k1
get k2
get k3
set k1 1 120 10
JournalDev
set k2 0 120 8
testword
set k3 2 5 10
JournalDev
get k3
get k2
get k1
flush_all
quit
```
![2.1](https://github.com/IMiroxxI/redis-memcached/blob/main/2/2.1.png)

---

### Задание 4. Запись данных в Redis

Запишите в Redis несколько ключей с любыми именами и значениями. 

*Через redis-cli достаньте все записанные ключи и значения из базы, приведите скриншот этой операции.*

### Ответ:
Установка Redis
```
sudo apt-get install redis 
```
Проверка статуса Redis
```
sudo systemctl status redis
```
Команды Redis
```
redis-cli

scan 0
set k1 test
set k2 100
scan 0
get k1
get k2
flushall
exit
```
![3.1](https://github.com/IMiroxxI/redis-memcached/blob/main/3/3.1.png)
![3.2](https://github.com/IMiroxxI/redis-memcached/blob/main/3/3.2.png)

---
