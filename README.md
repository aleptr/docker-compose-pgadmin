# Docker Compose pgAdmin 4 Setup

simple Docker Compose configuration for running pgAdmin 4 in a containerized environment.

## Overview

This project provides a ready-to-use Docker Compose setup for pgAdmin 4, α web-based administration tool for PostgreSQL databases. 
The configuration includes persistent data storage and environment-based configuration.

## Features

- **Latest pgAdmin 4**: Uses the latest official `dpage/pgadmin4:latest` image
- **Persistent Storage**: Data is stored in a named Docker volume
- **Environment Configuration**: Easy configuration through environment variables

## Prerequisites

- Docker
- Docker Compose

## Quick Start
1. **Clone the repository**
    ```shell script
    git clone <repository-url>
    cd docker-compose-pgadmin
    ```

2. **Set up the environment variables**

    Copy the `.env.example` file to a new `.env` in order to add your secrets. 
    ```shell script
    cp .env.example .env
    ```

3. **Configure your environment**

    Edit the `.env` file and set the required values:
    ```
    PGADMIN_DEFAULT_EMAIL=your-email@example.com
       PGADMIN_DEFAULT_PASSWORD=your-secure-password
       PGADMIN_PORT=5050
    ```

4. **Start the service**:

    Run the following to start the service
    ```shell script
    docker-compose up -d
    ```

5. **Access pgAdmin**:

    Open your browser and navigate to `http://localhost:5050` (or the port you configured). In the login page use the credentials you specified in the `.env` file.

## Configuration

### Environment Variables

| Variable                   | Description                                 | Required |
|----------------------------|---------------------------------------------|----------|
| `PGADMIN_DEFAULT_EMAIL`    | Default login email for pgAdmin             | Yes      |
| `PGADMIN_DEFAULT_PASSWORD` | Default login password for pgAdmin          | Yes      |
| `PGADMIN_PORT`             | Host port to map to pgAdmin (default: 5050) | Yes      |

### Data Persistence

The configuration includes a named volume `my-data` that persists pgAdmin data at `/var/lib/pgadmin` inside the container. 
This ensures your server configurations and settings are retained between container restarts.


## Contributing
You are more than welcome to provide feedback or any contribution.

## License

This project is licensed under the terms specified in the LICENSE file.