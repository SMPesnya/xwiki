# Структура проекта
├── docker-compose.yml - yaml файл для docker compose<br/>
├── LICENSE            - лицензия LGPL<br/>
└── README.md          - этот файл <br/>

# Как установить и запустить xwiki
## Создание директорий для разделов в контейнерах xwiki и xwiki-postgres  
  ```bash
     sudo mkdir -p /home/docker/xwiki
     sudo mkdir -p /home/docker/postgres/xwiki
     sudo chown root:docker -R /home/docker
  ```
> Если тебе не подходит текущие пути для хранения разделов замени их на что-то другое в разделе volumes:
> Или добавь volumes, например для xwiki-data
  ```yaml
     volumes:
      - xwiki-data:/usr/local/xwiki 
  ```	
> Пример для xwiki-postges-data
  ```yaml
     volumes:
      - xwiki-postgres-data:/var/lib/postgresql/data
  ```	
> В конце файла добавь
  ```yaml
    volumes:
     - xwiki-data
     - xwiki-postgres-data
  ```
## Скачивание образов и запуск контейнеров 
  ```bash
     docker-compose up -d # скачает образы, запустит контейнеры с нужными настройками
  ```
## Запуск уже существующих контейнеров
  ```bash
     docker-compose start -d # запустит уже существующие контейнеры 
  ```
## Остановка контейнера
  ```bash
     docker-compose stop # остановит запущенные контейнеры
  ```
## Остановка и удаление
  ```bash
     docker-compose down # остановит контейнеры и удалит их, а так-же их образы 
  ```
