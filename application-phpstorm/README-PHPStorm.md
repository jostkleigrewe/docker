# docker
All around Docker 

- nginx
- MySQL 8
- PHP 8.2



# Docker Compose

docker compose --project-name "docker-repo-test" --env-file .env --file compose.yaml .

docker compose -f docker-compose.yml -f docker-compose.admin.yml run backup_db

