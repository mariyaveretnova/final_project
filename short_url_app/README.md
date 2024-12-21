**Запуск shorturl_app локально**

1. Скачиваем папку с файлами на свой локальный компьютер;
2. Запускаем приложение Docker;
3. Из папки shorturl_app открываем терминал и вводим следующие команды:
   - docker build -t shorturl_app . для сборки docker-образа;
   - docker run -d -p 8001:80 -v shorturl_data:/app/data shorturl_app для запуска контейнера с подключением тома для хранения данных;
   - docker ps для проверки, что контейнер запустился.
4. Заходим на http://localhost:8001/docs и видим развернутый сервис: с помощью "Try it out" можем принимать URL, возвращая короткую ссылку, перенаправлять на исходный URL, получать статистику о кликах и удалять записи (**функция удаления добавлена студентом**);
6. Вводим docker stop <container_id> или docker stop <container_name> для остановки контейнера по окончании работы.

**Запуск short_url_app через DockerHub**

1. В терминале пишем docker run -d -p 8001:80 -v shorturl_data:/app/data mariyaveretnova/shorturl-service:latest (образ сервиса доступен в DockerHub в моем репозитории, поэтому я могу запускать его отовсюду, где имеется доступ к DockerHub).