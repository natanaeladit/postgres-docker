# postgres-docker

```
docker pull postgres

docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v /d/Postgres:/var/lib/postgresql/data postgres

docker exec -it pg-docker sh

createdb -U postgres mydb

psql -U postgres mydb

\l

select version();

select current_date;

```
