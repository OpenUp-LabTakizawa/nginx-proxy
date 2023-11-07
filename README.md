<h1 align="center">nginx-proxy</h1>

<p align="center">
  <a aria-label="docker" href="https://www.docker.com/">
    <img alt="" src="https://img.shields.io/badge/-docker-2496ED.svg?logo=docker&style=for-the-badge&labelColor=000000">
  </a>
  <a aria-label="nginx" href="https://nginx.org/">
    <img alt="" src="https://img.shields.io/badge/-nginx-009639.svg?logo=nginx&style=for-the-badge&labelColor=000000">
  </a>
  <a aria-label="License" href="https://github.com/OpenUp-LabTakizawa/nginx-proxy/blob/main/LICENSE">
    <img alt="" src="https://img.shields.io/github/license/OpenUp-LabTakizawa/nginx-proxy?style=for-the-badge&labelColor=000000">
  </a>
</p>

<p align="center">
  Set up a container running nginx and docker-gen with SSL certificates automatically:robot:
</p>

## Usage

### 1. Clone
To clone and run this application, you'll need [Git](https://git-scm.com) and [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed on your computer. From your command line:

```bash
# Clone this repository
$ git clone https://github.com/OpenUp-LabTakizawa/nginx-proxy
```

### 2. Set variables in the .env file
https://github.com/OpenUp-LabTakizawa/nginx-proxy/blob/eccfc56bfb6aa6d7d0a30bc93ecee517b45459a9/.env#L1-L2

`DEFAULT_EMAIL` is used by Let's Encrypt in order to warn you about expiring certificates and allow you to recover your account.  
`NETWORK` is whatever you like.

```
# For example
DEFAULT_EMAIL=example@gmail.com
NETWORK=nginx_web
```
### 3. Docker Compose
```bash
# Create a new docker network which you set at NETWORK variable in the .env file
$ docker network create nginx_web

# Check if variables are appropriate
$ docker compose convert

# Run and up the containers using docker compose
$ docker compose up -d

# Make sure if there are errors in the containers
$ docker compose logs
```

## Credits

This software uses the following open source packages:

- [Docker](https://www.docker.com/)
- [Nginx](https://nginx.org/)
- [docker-gen](https://github.com/nginx-proxy/docker-gen)
- [nginx-proxy](https://github.com/nginx-proxy/nginx-proxy)
- [acme-companion](https://github.com/nginx-proxy/acme-companion)

## License

The Apache License Version 2.0 (2023) - [OpenUp-LabTakizawa](https://github.com/OpenUp-LabTakizawa).
Please have a look at the [LICENSE](https://github.com/OpenUp-LabTakizawa/nginx-proxy/blob/main/LICENSE) for more details.
