# Inception

[![42 Project](https://img.shields.io/badge/42-Project-1f425f.svg)](https://42.fr)
[![Docker](https://img.shields.io/badge/Built%20with-Docker-blue?logo=docker)](https://www.docker.com/)
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen)]()

> A fully containerized, secure, and scalable web infrastructure hosted using Docker.  
> Made by [ERROR244](https://github.com/ERROR244).

![inception-demo](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExaGRmM2tja3M0azExdTc4a3ViMmlwMzhkdXFrbWN5enZ6MnduM2NvYSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/qgQUggAC3Pfv687qPC/giphy.gif)

---

## Project Structure

```bash
Inception/
├── Makefile
├── docker-compose.yml
└── srcs/
└───── .env             #(just for testing)
└───── requirements/
├───────── mariadb/
├───────── wordpress/
├───────── nginx/
└───────── bonus/
├──────────── Website/
├──────────── redis/
├──────────── ftp/
├──────────── adminer/
└──────────── portainer/
```


---

## Services

| Service     | Description                               | Port(s)     |
|-------------|-------------------------------------------|-------------|
| **Nginx**   | Reverse proxy with SSL                    | `443`       |
| **WordPress** | CMS for content management             | `9000`      |
| **MariaDB** | Relational database for WordPress         | `3306`      |
| **Redis**   | Caching layer                              | `6379`      |
| **FTP**     | File Transfer Protocol server              | `21`, `21000-21010` |
| **Adminer** | DB admin panel for MariaDB                 | `8800`      |
| **Portainer** | Docker container manager UI             | `9443`      |
| **Website** | Custom static site                         | `8000`      |

---

## Makefile Usage

| Command     | Description                                           |
|-------------|-------------------------------------------------------|
| `make build`| Build and run all containers                          |
| `make up`   | Start all containers in detached mode                 |
| `make stop` | Stop all running containers                           |
| `make down` | Stop and remove all containers and volumes            |
| `make Down` | Hard reset: remove volumes' content + containers      |
| `make ps`   | Show container status                                 |
| `make logs` | Show container logs                                   |
| `make reUp` | Restart after `down`                                  |
| `make reBuild` | Rebuild from scratch                              |

---

## Features

- SSL (HTTPS) enabled via Nginx
- Secure password and user management through environment variables
- Persistent volumes for MariaDB and WordPress
- Bonus services for enhanced DevOps & monitoring
- Clean Docker architecture with network isolation

---

## How to Run

1. **Clone the repo**  
   
   ```bash
   git clone https://github.com/ERROR244/Inception.git
   cd Inception
   ```

2. Run the project

   ```bash
   make build
   ```

3. Access services

   - WordPress: https://localhost:443
   - Website: http://localhost:8000
   - Adminer: http://localhost:8800
   - Portainer: https://localhost:9443
   - FTP: (if ftp is installed on your machine)
      ```bash
      ftp localhost 21
      ```
      Then enter your username and password from the .env file when prompted.

## 42 Subject Goals

- Set up multi-container Docker architecture
- Isolate services via volumes and networks
- Use only Docker CLI and Compose (no Dockerfiles from hub)
- Secure the services with SSL
- Bonus: Add extra services of your choice


### Authors

- [ERROR244](https://github.com/ERROR244)

### 📜 License
MIT — Free to use, modify, and share.
