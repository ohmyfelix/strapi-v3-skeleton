# Strapi v3 Skeleton

[Strapi](https://strapi.io/) - Open Source Node.js Headless CMS

## Stack

- Strapi 3+
- Node.js 16.x
- PostgreSQL, MySQL/MariaDB, or SQLite

## Local development

Copy the environment template, adjust it for your local database, install dependencies, and start Strapi:

```bash
cp .env.example .env
make install
make dev
```

Strapi is available at [http://localhost:1337](http://localhost:1337); create and manage CMS users at [http://localhost:1337/admin](http://localhost:1337/admin).

## Database configuration

`config/database.js` supports `DATABASE_TYPE=postgres`, `mysql`, and `sqlite`. PostgreSQL and MySQL/MariaDB use `DATABASE_URL`; SQLite uses `DATABASE_FILENAME` and defaults to `.tmp/data.db`. Set the matching variables in `.env` rather than relying on the sample credentials.

## Docker database services

`docker-compose.yml` provides database services only: MariaDB on [localhost:3306](http://localhost:3306), PostgreSQL on [localhost:5432](http://localhost:5432), and Adminer on [http://localhost:8080](http://localhost:8080). Start them with:

```bash
make docker-up
```

For the bundled PostgreSQL service, configure `DATABASE_TYPE=postgres` and a PostgreSQL `DATABASE_URL` in `.env`. For MariaDB, use `DATABASE_TYPE=mysql` and a MySQL-compatible `DATABASE_URL`.

## Commands

```bash
make install       # install locked dependencies
make dev           # run Strapi in development mode
make start         # build and start Strapi
make strapi-build  # build the Strapi admin
make clean         # remove Strapi build caches
```
