1) Дан код на golang - простейший веб-сервер, слушается на порту 3000 (файл main.go). Нужно написать Dockerfile, в котором будет собран бинарный файл (команда ```go build -o /path/to/binary_file /path/to/main.go```) и запустить из него контейнер.
Итоговый результат: команда 
```
curl 127.0.0.1:3000 
```
отдает Hello World

2) Запустить с помощью docker compose mysql:8 (минимум в описании нужно указать переменную MYSQL_ROOT_PASSWORD)
