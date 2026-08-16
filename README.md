# Strapi v3 Skeleton

A [Strapi](https://strapi.io/) 3 application skeleton: an open-source Node.js headless CMS configured for local development and deployment. Acquire it by cloning this repository or using it as a GitHub template.

## Requirements

- Node.js 16.x
- npm
- Docker Compose (optional, for database services)

## Create a project and run locally

Clone the repository, copy the environment template, choose database settings, install dependencies, and start Strapi:

```bash
git clone https://github.com/contributte/strapi-v3-skeleton.git acme
cd acme
cp .env.example .env
make install
make dev
```

Strapi is available at [http://localhost:1337](http://localhost:1337) and its administration interface at [http://localhost:1337/admin](http://localhost:1337/admin).

## Commands

```bash
make install       # install locked dependencies
make dev           # run Strapi in development mode
make strapi-build  # build the Strapi admin
make start         # build and start Strapi
```

## Configuration

Copy `.env.example` to `.env`. Its values, including all sample secrets and credentials, are for development only and must be replaced for deployment.

### Application

`HOST` and `PORT` configure the HTTP listener. `ADMIN_JWT_SECRET` configures administrator authentication. The Vercel integration reads `VERCEL_TOKEN`, `VERCEL_TEAM_ID`, `VERCEL_PROJECT_ID`, and `VERCEL_TRIGGER_PRODUCTION`.

### Database

`config/database.js` supports `DATABASE_TYPE=postgres`, `mysql`, and `sqlite`. PostgreSQL and MySQL/MariaDB use `DATABASE_URL`; SQLite uses `DATABASE_FILENAME` and defaults to `.tmp/data.db`. Set the matching variables in `.env` rather than relying on the sample credentials.

### Optional upload integrations

The upload configuration uses ImageKit variables (`IMAGEKIT_FOLDER`, `IMAGEKIT_PUBLIC_KEY`, `IMAGEKIT_PRIVATE_KEY`, `IMAGEKIT_URL`) for images and AWS-compatible variables (`AWS_BUCKET`, `AWS_ENDPOINT`, `AWS_ACCESS_KEY_ID`, `AWS_ACCESS_SECRET`) as its fallback.

## Docker database services

`docker-compose.yml` provides database services only: MariaDB on [localhost:3306](http://localhost:3306), PostgreSQL on [localhost:5432](http://localhost:5432), and Adminer on [http://localhost:8080](http://localhost:8080). Start them with:

```bash
make docker-up
```

For the bundled PostgreSQL service, configure `DATABASE_TYPE=postgres` and a PostgreSQL `DATABASE_URL` in `.env`. For MariaDB, use `DATABASE_TYPE=mysql` and a MySQL-compatible `DATABASE_URL`. The Compose credentials are development-only.
