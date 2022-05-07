# Vue.js Quickstart

This is a Vue.js Static Site Quickstart for [Nullstone](https://nullstone.io).
This is based off the official Vue.js [Quick Start](https://vuejs.org/guide/quick-start.html) guide.

This quickstart is set up with:
- Vue.js 3
- Typescript
- Vue router for Single Page Application

## Running locally

You can run this project locally inside Docker or using rails alone.
To use Docker, this project contains `docker-compose.yml` that runs with `RAILS_ENV=development`.
This ensures that using Docker doesn't prohibit handy development features:
- Assets are compiled on demand.
- Pretty error logs are displayed in the browser.
- Hot reload is configured so that changes to rails files doesn't require a docker rebuild or restart.

To run using Docker locally, use docker compose:
```shell
docker compose up
```

Then, visit [http://localhost:3000](http://localhost:3000).

## How to launch via Nullstone

1. Create a static site. (Remember `app-name` for later)
2. Add a subdomain. (this will add a CDN capability)
3. Provision
  ```shell
  nullstone up --wait --block=<app-name> --env=<env-name>
  ```
4. Build, push, and deploy
  ```shell
  npm run build
  nullstone launch --source=./dist --app=<app-name> --env=<env-name>
  ```

### Hot reload

The `app` in `docker-compose.yml` is configured to automatically reload changes to files.
You do not need to rebuild/restart the app when making changes to code.

### Update dependencies

To make changes to dependencies, make changes to `Gemfile` and restart your docker container.
`bundle install` happens automatically at the boot of the docker container to update dependencies.

```shell
docker compose restart app
```

## Details on quickstart

This static site was generated following these steps.
1. `npm init vue .`
2. `npm install`
