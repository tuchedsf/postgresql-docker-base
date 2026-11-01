# README

## ARQUIVO ENV
- crie um arquivo .env na pasta com o seguinte conteudo:

```
POSTGRES_USER=devadmin
POSTGRES_PASSWORD=SUASENHAAQUI
POSTGRES_DB=dev
```
substiua a senha por uma nova.


## Criar base de dados
```
docker exec -it postgres-dev \
  psql -U devadmin -d dev
```

## Criar usuarios:

```
CREATE USER api_user WITH PASSWORD 'senha_api';
CREATE DATABASE projeto_api OWNER api_user;
```
## Aplicações executando no mac:

```
DB_HOST=localhost
DB_PORT=5432
DB_NAME=projeto_api
DB_USER=api_user
DB_PASSWORD=senha_api
```

## Aplicações executando no docker:

```
DB_HOST=postgres-dev
DB_PORT=5432
DB_NAME=projeto_api
DB_USER=api_user
DB_PASSWORD=senha_api
```

## comandos úteis

| Ação | Comando | 
| -------- | ----------- |
| Iniciar | docker start postgres-dev|
| Parar | docker stop postgres-dev |
| Reiniciar| docker restart postgres-dev |
| Logs | docker logs -f postgres-dev |
| Acessar terminal SQL | docker exec -it postgres-dev psql -U devadmin -d dev |
| Ver databases | docker exec postgres-dev psql -U devadmin -d dev -c "\l" |
| Ver volume | docker volume inspect postgres_dev_data |
| Parar e apagar todos os dados*** | docker compose down -v |
