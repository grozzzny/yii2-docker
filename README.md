# Настройка рабочего окружения в Docker для yii-framework приложения (Yii2)

## Быстрая настройка
### 1. Установить Git, Docker и Docker-Compose
- [Git Install documentation](https://git-scm.com/downloads)
- [Docker Install documentation](https://docs.docker.com/install/)
- [Docker-Compose Install documentation](https://docs.docker.com/compose/install/)

### 2. Склонировать проект и перейти в директорию приложения
```
git clone https://github.com/grozzzny/yii2-docker.git nameApp && cd nameApp
```

### 3. В файле docker/docker-compose.yml можно задать порт:
```yml
ports:
   - 75:80
```

### 4. Запустить контейнер с названием проекта "name-app", выполнив команду
```bash
docker-compose -p name-app -f docker/docker-compose.yml up -d
```

### 5. В контейнере выполнить установку Yii2 basic во временную директорию "app"
```bash
composer create-project --prefer-dist yiisoft/yii2-app-basic app
cp -R app/* . && rm -rf app
```

Или выполнить команду вне контейнера:

```bash
docker exec -it name-app-php-1 bash -c 'composer create-project --prefer-dist yiisoft/yii2-app-basic app && cp -R app/* . && rm -rf app'
```

### 6. Доступ приложения

Когда ваш контейнер docker запущен, подключитесь к нему по порту `75`.

[http://127.0.0.1:75](http://127.0.0.1:75)


### 7. Ссылки

[Официальный Docker-образ Yii2.](https://github.com/yiisoft/yii2-docker)