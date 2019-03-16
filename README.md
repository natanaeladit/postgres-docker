# postgres-docker

```
docker pull postgres

docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v c:/Postgres:/var/lib/postgresql/data postgres

docker exec -it pg-docker sh

createdb -U postgres mydb

psql -U postgres mydb

\l

select version();

select current_date;

CREATE TABLE people (id int, name varchar(80));

INSERT INTO people (id,name) VALUES (1, 'People 1');

SELECT * FROM people;

\q

exit

docker stop pg-docker

```
