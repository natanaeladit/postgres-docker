# postgres-docker

```
mkdir postgres
cd postgres

docker volume create --driver local --name=pgvolume

create a file named pg-env.list containing:
PG_MODE=primary
PG_PRIMARY_USER=postgres
PG_PRIMARY_PASSWORD=yoursecurepassword
PG_DATABASE=testdb
PG_USER=yourusername
PG_PASSWORD=yoursecurepassword
PG_ROOT_PASSWORD=yoursecurepassword
PG_PRIMARY_PORT=5432

docker network create --driver bridge pgnetwork

docker run --publish 5432:5432 --volume=pgvolume:/pgdata --env-file=pg-env.list --name=postgres --hostname=postgres --network=pgnetwork --detach postgres

docker volume create --driver local --name=pga4volume

create a file named pgadmin-env.list containing:
PGADMIN_SETUP_EMAIL=youremail@yourdomain.com
PGADMIN_SETUP_PASSWORD=yoursecurepassword
SERVER_PORT=5050

docker run --publish 5050:5050 --volume=pga4volume:/var/lib/pgadmin --env-file=pgadmin-env.list --name=pgadmin4 --hostname=pgadmin4 --network=pgnetwork --detach crunchydata/crunchy-pgadmin4:centos7-10.4-2.0.0
```
