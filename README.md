# RapidMCP - Self-hosted edition

https://rapid-mcp.com

Self hosted edition of RapidMCP. 

## Background

Convert your REST API into MCP servers in minutes!

Transform your existing APIs into AI-agent-ready MCP servers with zero code changes. Just plug in your API and go—no backend modifications needed.


## Demo

![Home](/assets/screen-1.png)

![Login](/assets/screen-2.png)

![Severs](/assets/screen-3.png)



## Architecture

Deploy using Docker Compose on your VM. If you're familiar with Docker Compose, setup will be a breeze.

## Basic setup

### 1. Clone the repo and configure `.env`

- When you are on the vm, run the following.
- Ensure to update `EE_LICENSE_KEY`

```
git clone https://github.com/joshuaheslin/rapid-mcp-self-hosted.git
cd rapid-mcp-self-hosted/docker-compose
cp .env.example .env
# Update EE_LICENSE_KEY and any other necessary values
```


### 2. Authenticate docker image pull

Instructions for authentication will be provided after purchase.

### 3. Start the services

```
docker compose up -d
```

This launches the containers and Postgres.
Ensure your VM has public access if you're setting up a domain/DNS.

### 🔁 Version change 

To upgrade images, bump the versions in docker-compose.yaml and restart:

```
docker compose restart -d
```


### ⛔ Stopping the stack

```
docker compose stop -d
```


## Your Data

Your data is stored inside a Docker volume for Postgres, typically here:
/var/lib/postgresql/data — it's entirely yours.


## Domain

The app runs on `0.0.0.0:80` by default.
Update your DNS to point to your VM’s external IP.

- If using Cloudflare, it can handle TLS termination.
- Otherwise, you'll need to handle SSL termination on the server.


# ✅ Ready to Get Started?

1. Sign up at https://rapid-mcp.com and choose a paid plan that includes self-hosted support.

2. You’ll automatically receive your license key and Docker image credentials.

3. (Optional) Book a call with our team for deployment or support.


👋 Need Help? Join us on Discord for support or questions!




