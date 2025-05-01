# Node.js with PostgreSQL, Redis, and Valkey Dev Container

This project provides a development environment with Node.js, PostgreSQL, Redis, and optional Valkey (Redis alternative) using Docker containers. It's configured as a VS Code Dev Container for seamless development.

## 🚀 Features

- **Node.js**: Express.js API with PostgreSQL connection
- **PostgreSQL**: Database server with pgAdmin web interface
- **Redis**: In-memory data store with RedisInsight management UI
- **Valkey**: Alternative to Redis (commented out by default)
- **Dev Container**: Pre-configured VS Code development environment

## 📋 Prerequisites

- [Docker](https://www.docker.com/products/docker-desktop/) and Docker Compose
- [Visual Studio Code](https://code.visualstudio.com/)
- [VS Code Remote - Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## 🛠️ Setup

1. Clone this repository
2. Create an `.env` file in the `app` directory with the following content:

```
PORT=3000
DB_HOST=postgres
DB_PORT=5432
DB_USER=admin
DB_PASSWORD=password
DB_NAME=mydatabase
```

3. Open the project in VS Code
4. When prompted, click "Reopen in Container" or run the "Remote-Containers: Reopen in Container" command
5. Wait for the containers to build and start

## 🏃‍♂️ Running the Application

The application should start automatically when the container is built. You can access:

- Node.js API: http://localhost:3000
- pgAdmin: http://localhost:5050 (Email: admin@admin.com, Password: password)
- RedisInsight: http://localhost:5540

## 📝 API Endpoints

- `GET /`: Health check endpoint
- `POST /add-random-user`: Adds a random user to the PostgreSQL database

## 🧰 Container Services

| Service | Description | Port |
|---------|-------------|------|
| nodejs | Node.js application | 3000 |
| postgres | PostgreSQL database | 5432 |
| pgadmin | PostgreSQL admin interface | 5050 |
| redis | Redis server | 6379 |
| redisinsight | Redis management UI | 5540 |
| valkey | Valkey server (commented out) | 6379 |

## 🔐 Default Credentials

- **PostgreSQL**:
  - User: admin
  - Password: password
  - Database: mydatabase

- **pgAdmin**:
  - Email: admin@admin.com
  - Password: password

- **Redis**:
  - Password: myredispassword

- **Valkey**:
  - Password: myvalkeypassword

## 📂 Project Structure

```
.
├── .devcontainer/          # Dev container configuration
├── app/                    # Node.js application
│   ├── Dockerfile          # Node.js Dockerfile
│   ├── index.js            # Main application file
│   └── package.json        # Node.js dependencies
└── docker-compose.yml      # Docker Compose configuration
```

## 🔧 Customization

- Modify `docker-compose.yml` to adjust container configurations
- Update `.devcontainer/devcontainer.json` to customize the development environment
- Edit `app/index.js` to modify the Node.js application

## 📚 Technologies

- Node.js 22.15.0
- Express.js 4.18.2
- PostgreSQL 16.8
- Redis 7.4.3
- pgAdmin 9.2.0
- RedisInsight 2.68.0
- Valkey 8.1.1 (Recommended)