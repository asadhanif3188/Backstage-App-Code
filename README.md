# [Backstage](https://backstage.io)

This is your newly scaffolded Backstage App, Good Luck!

To start the app, run:

```sh
yarn install
yarn start
```

## Few Screenshots

<img src="screenshots/1.front-page.png" width="90%" />
<br>
<img src="screenshots/2.github-popup.png" width="90%" />
<br>
<img src="screenshots/3.components-page.png" width="90%" />
<br>


## Setup Techdocs in Backstage

We need to run following commands within the container to enable techdocs.

```
apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    rm -rf /var/lib/apt/lists/*

export VIRTUAL_ENV=/opt/venv

python3 -m venv $VIRTUAL_ENV

export PATH="$VIRTUAL_ENV/bin:$PATH"

pip3 install mkdocs-techdocs-core
```

## Postgres DB for Backstage

Following command can spin up a postgres container.

```
docker run -d --name backstage-postgres -e POSTGRES_USER=backstage -e POSTGRES_PASSWORD=backstage -e POSTGRES_DB=backstage -e PGDATA=/var/lib/postgresql/data/pgdata -v /home/ubuntu/psql:/var/lib/postgresql/data postgres:16
```



## Building Production Grade Docker Image for Backtage

**Ref:** `https://backstage.io/docs/deployment/docker`

Command to build the Backend for Production
`yarn build:backend --config ../../app-config.yaml  --config ../../app-config.production.yaml`

