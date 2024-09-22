# Шаг 1 - билд приложения

# Стягиваем образ ноды с docker hub
FROM node:18.0.0-alpine AS nodeimg

# Назначаем рабочика каталог
WORKDIR /usr/src/app

# Закидываем сырое js-приложение в образ для биджинга
COPY ["./my-app", "./"]

# Билдим js-приложение, избовляясь от хависимостей
RUN npm install && npm run build

# Шаг 2 - деплой сбилденного js-приложение в nginx

# Стягиваем последнюю версию образа nginx с docker hub
FROM nginx

# Копируем сбилднное js-приложение (без мусора/зависимостей) в nginx
COPY --from=nodeimg /usr/src/app/build /var/www/app

# Говорим, что внутри контейнера nginx слушает 80 порт, и на него надо мапить внешний хостовый порт
EXPOSE 80

# Запускаем nginx
ENTRYPOINT ["nginx", "-g", "daemon off;"]