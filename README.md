### Домашнее задание к занятию 14 «Средство визуализации Grafana».
### Обязательные задания.
### Задание 1.
1.Используя директорию help внутри этого домашнего задания, запустите связку prometheus-grafana.

2.Зайдите в веб-интерфейс grafana, используя авторизационные данные, указанные в манифесте docker-compose.

3.Подключите поднятый вами prometheus, как источник данных.

4.Решение домашнего задания — скриншот веб-интерфейса grafana со списком подключенных Datasource.

### Ответ.
<img width="1280" height="800" alt="Скрин1" src="https://github.com/user-attachments/assets/9e299d76-1390-465e-8749-e2507cd144c8" />

### Задание 2.
### Изучите самостоятельно ресурсы:
1.PromQL tutorial for beginners and humans.

2.Understanding Machine CPU usage.

3.Introduction to PromQL, the Prometheus query language.

### Создайте Dashboard и в ней создайте Panels:

1.Утилизация CPU для nodeexporter (в процентах, 100-idle);

2.CPULA 1/5/15;

3.Количество свободной оперативной памяти;

4.Количество места на файловой системе.
### Для решения этого задания приведите promql-запросы для выдачи этих метрик, а также скриншот получившейся Dashboard.

### Ответ.
<img width="1280" height="800" alt="Скрин2" src="https://github.com/user-attachments/assets/4bc7f811-bcd9-4069-93aa-3b9d7cdb51ae" />

### PromQL-запросы:
### 1.Утилизация CPU, % (100 − idle)
100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)

### 2.CPU Load Average 1 / 5 / 15
node_load1

node_load5

node_load15
### 3.Свободная оперативная память.
node_memory_MemAvailable_bytes

### 4.Свободное место на файловой системе.
node_filesystem_avail_bytes{mountpoint="/",fstype!~"tmpfs|devtmpfs|overlay|squashfs"}

### Задание 3.

Создайте для каждой Dashboard подходящее правило alert — можно обратиться к первой лекции в блоке «Мониторинг».

В качестве решения задания приведите скриншот вашей итоговой Dashboard.

### Ответ.








