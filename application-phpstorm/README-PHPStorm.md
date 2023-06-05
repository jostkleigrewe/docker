# docker
All around Docker 

- nginx
- MySQL 8
- PHP 8.2



# Docker Compose

docker compose --project-name "docker-repo-test" --env-file .env --file compose.yaml .

docker compose -f docker-compose.yml -f docker-compose.admin.yml run backup_db

docker compose up -d --build

docker compose down

### Symfony App benutzen
docker compose exec php symfony --version

### Symfony App benutzen
docker compose exec php bin/console


### PHP benutzen
docker compose exec php composer -v
