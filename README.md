# Vue.js Quickstart

This is a Vue.js Static Site Quickstart for [Nullstone](https://nullstone.io).
This is based off the official Vue.js [Quick Start](https://vuejs.org/guide/quick-start.html) guide.

This quickstart is set up with:
- Vue.js 3
- Typescript
- Vue router for Single Page Application

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

## Running locally

You can run this project locally inside Docker or using a dev server.
The docker setup is configured to hot reload; you don't have to rebuild/restart the container when you change code.

### Docker

NOTE: This setup requires configuring vite server to bind on `0.0.0.0`.

```shell
docker compose up
```

Visit [http://localhost:3000](http://localhost:3000).

### Dev Server

```shell
npm run dev
```

Visit [http://localhost:3000](http://localhost:3000).

### Hot reload

The `app` in `docker-compose.yml` is configured to automatically reload changes to code.
You do not need to rebuild/restart the app when making changes to code.

### Update dependencies

To make changes to dependencies, make changes to `package.json` and restart your docker container.
`npm install` happens automatically at the boot of the docker container to update dependencies.

```shell
docker compose restart app
```

## Details on quickstart

This static site was generated following these steps.
1. `npm init vue .`
2. `npm install`
3. Configure `package.json` to serve on `0.0.0.0` (necessary for Docker setup)
  ```json
  "scripts": {
    "dev": "vite --host=0.0.0.0",
  ```
