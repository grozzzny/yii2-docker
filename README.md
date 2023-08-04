# Настройка рабочего окружения в Docker для yii-framework приложения

## Быстрая настройка
### 1. Установить Git, Docker и Docker-Compose
- [Git Install documentation](https://git-scm.com/downloads)
- [Docker Install documentation](https://docs.docker.com/install/)
- [Docker-Compose Install documentation](https://docs.docker.com/compose/install/)

### 2. Склонировать проект и перейти в директорию приложения
```
git clone https://github.com/grozzzny/yii2-docker.git nameApp
cd nameApp
```

### 3. В файле docker/docker-compose.yml можно задать порт:
```yml
ports:
   - 75:80
```

### 4. запустить контейнер, выполнив команду
```bash
docker-compose -p name-app -f docker/docker-compose.yml up -d
```

### 5. В контейнере выполнить установку Yii2
```bash
composer create-project --prefer-dist yiisoft/yii2-app-advanced .
```

Или выполнить команду вне контейнера:

```bash
docker exec -it name-app-php-1 composer create-project --prefer-dist yiisoft/yii2-app-advanced .
```

### 8. Доступ приложения

Когда ваш контейнер docker запущен, подключитесь к нему по порту `75`.

[http://127.0.0.1:75](http://127.0.0.1:75)


### 8. Ссылки

[Официальный Docker-образ Yii2.](https://github.com/yiisoft/yii2-docker)