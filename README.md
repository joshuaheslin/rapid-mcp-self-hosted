# RapidMCP - Self-hosted edition

https://rapid-mcp.com

https://docs.rapid-mcp.com

Self hosted edition of RapidMCP. 

## Background

Convert your REST API into MCP servers in minutes!

Transform your existing APIs into AI-agent-ready MCP servers with zero code changes. Just plug in your API and go—no backend modifications needed.

## Live video

https://www.youtube.com/watch?v=YBJNgJrwWFE

[![Youtube video](https://img.youtube.com/vi/YBJNgJrwWFE/0.jpg)](https://www.youtube.com/watch?v=YBJNgJrwWFE)

## Demo

![Home](/assets/screen-1.png)

![Login](/assets/screen-2.png)

![Severs](/assets/screen-3.png)




## Architecture

Deploy using Docker Compose on your VM. If you're familiar with Docker Compose, setup will be a breeze. If not, we will schedule a call to see what works best for you.

## Basic setup

### 1. Clone the repo and configure `.env`

- When you are on the vm, run the following.
- Ensure to update `EE_LICENSE_KEY` in `.env` file
- Ensure to add `key.json` next to `.env`

```bash
git clone https://github.com/joshuaheslin/rapid-mcp-self-hosted.git
cd rapid-mcp-self-hosted/docker-compose
cp .env.example .env
# Update EE_LICENSE_KEY and any other necessary values
# all commands going forward are referenced from this dir.
```

Your current directory should look like this:

```
➜  docker-compose git:(main) ✗ ls -al
total 32
drwxr-xr-x@  7 root  staff   224 Oct 27 17:50 .
drwxr-xr-x@ 10 root  staff   320 Jun 14 17:52 ..
-rw-r--r--@  1 root  staff   429 Jun 14 18:31 .env
-rw-r--r--@  1 root  staff  1017 Jun 14 17:00 .env.example
-rw-r--r--@  1 root  staff  1455 Jun 14 19:06 docker-compose.yml
-rw-r--r--@  1 root  staff     0 Oct 27 17:50 key.json
-rw-r--r--@  1 root  staff   403 Jun 14 16:42 nginx.conf
```

### 2. Authenticate docker image pull

Use docker login to authentication with the container registry. You only have to do this once.

```bash
nano key.json # paste the json key provided to you
cat ~/key.json | docker login -u _json_key --password-stdin https://us-central1-docker.pkg.dev
```

### 3. Start the services

```bash
docker compose up -d
```

This launches the containers and Postgres.
Ensure your VM has public access if you're setting up a domain/DNS.

### 🔁 Version change 

To upgrade images, bump the versions in docker-compose.yaml and restart:

```bash
docker compose restart -d
```


### ⛔ Stopping the stack

```bash
docker compose stop -d
```


## Your Data

Your data is stored inside a Docker volume for Postgres, typically here:
`/var/lib/postgresql/data` on the vm — it's entirely yours.


## Domain

The app runs on `0.0.0.0:80` by default.
Update your DNS to point to your VM’s external IP.

- If using Cloudflare, it can handle TLS termination.
- Otherwise, you'll need to handle SSL termination on the server.


## What you get after upgrading?

You will get the following values from RapidMCP team after purchase. This is all you've need from us.

1) `EE_LICENSE_KEY` (license for the product to put in .env)
2) `key.json`  (docker pull credentials)

# ✅ Ready to Get Started?

1. Sign up at https://rapid-mcp.com and choose a paid plan that includes self-hosted support.

2. You’ll automatically receive your license key and Docker image credentials.

3. (Optional) Book a call with our team for deployment or support.


👋 Need Help? Join us on <a href="https://discord.com/invite/uWnVNj9QEQ">Discord</a> for support or questions!

Or email josh@rapid-mcp.com

