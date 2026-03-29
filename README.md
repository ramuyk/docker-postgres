# Introduction

This repository provides a `docker-compose.yml` ready-to-use Docker configuration for setting up a PostgreSQL server with the PostGIS extension. The configuration is designed for quick deployment and includes a custom Dockerfile for the installation of PostGIS on the official PostgreSQL Docker container. For further details, please refer to the [PostgreSQL Docker documentation](https://hub.docker.com/_/postgres).

## Repository Contents

This repository contains:

- **Docker Compose File**: A `docker-compose.yml` file to configure the PostgreSQL Docker container with PostGIS. Notable features include:
  - **Persistent Data Storage**: Configures a volume:
    - `./volumes/data:/var/lib/postgresql/data` for preserving the PostgreSQL database files across container restarts.

  - **Environment Variables**: An `.env.example` file is provided with default credentials. Copy it to `.env` before starting the container — this file is used by `docker-compose.yml` to configure the initial PostgreSQL database.

- **Dockerfile**: Defines the custom build process for the `postgres-prod` Docker image. This includes the base PostgreSQL image and the PostGIS extension. You may add additional extensions or configurations by modifying the Dockerfile as necessary.

## Getting Started

### Quick Setup

1. **Clone the Repository**:
   Retrieve the configuration files from this repository using the following command:
   ```bash
   git clone https://github.com/ramuyk/docker-postgres.git
   cd docker-postgres
   ```

2. **Configure Environment Variables**:
   Copy the example environment file and edit it with your desired credentials:
   ```bash
   cp .env.example .env
   ```
   The `.env` file defines:
   - `POSTGRES_DB` — database name
   - `POSTGRES_USER` — superuser username
   - `POSTGRES_PASSWORD` — superuser password

   Be sure to change the default credentials before deploying to any non-local environment.

3. **Build and Start the PostgreSQL Service**:
   Execute the following command to build the PostgreSQL with PostGIS image and start the container:
   ```bash
   docker compose up -d --build
   ```

4. **Accessing the PostgreSQL Server**:
   Connect to your PostgreSQL database server using any PostgreSQL client with the credentials defined in your `.env` file.

