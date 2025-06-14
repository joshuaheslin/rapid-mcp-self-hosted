# RapidMCP - Self-hosted edition

https://rapid-mcp.com

Self hosted edition of RapidMCP. 

## Background

Convert your REST API into MCP Servers in minutes!

Transform your existing APIs into an MCP in minutes, with zero code changes. Simply plug in your API, and instantly convert it to an AI-agent ready MCP server - no backend modifications needed.


## Demo

![Home](/assets/screen-1.png)

![Login](/assets/screen-2.png)

![Severs](/assets/screen-3.png)



## Architecture

Deployment option is to run a docker compose on your own VM to run Rapid MCP in your infra.

If you are familiar with docker compose - this should be a piece of cake.


## Basic setup

When you are on the vm

```
git pull https://github.com/joshuaheslin/rapid-mcp-self-hosted.git

cd rapid-mcp-self-hosted/docker-compose

cp .env.example .env 
# (and update as needed)

docker compose up -d
```

It will start the db and containers. VM needs public access to setup your DNS record.

### Version change 

Bump the versions on the docker-compose.yaml as needed. 

```
docker compose restart -d
```


### Stop

```
docker compose stop -d
```


### Your Data

Your data is stored in postgres volume probably somewhere here (`/var/lib/postgresql/data`).

### Domain

The app will be available on 0.0.0.0:80 (on the machine).

Update your DNS to point to the externalIP of the VM. If you have Cloudflare proxy it can handle the TLS termination. Otherwise you'll need to.


