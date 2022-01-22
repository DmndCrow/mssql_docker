# SQL Server

This project lets you install **SQL Server** database using docker service.

## Prerequisites

Make sure you have installed these:
- [Docker and Docker Compose](https://phoenixnap.com/kb/install-docker-compose-on-ubuntu-20-04) - Will install all the required packages and software.
- [SQL Server command-line tools](https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver15) - Will install required sql server command line tools for connection using cmd.


## Installation

Make a copy of `.env.example` file named `.env`

```shell script
cp .env.example .env
```

---

Environment variables:
- **SQL Server settings**:
    - `SQL_PORT` - exposed port for **SQL Server**
    - `SQL_PASSWORD` - password for **SQL Server** for default user **SA**.
- `DATABASE_NETWORK` - network, on which our database will be accessible.

```dotenv
# MSSQL Server settings
MSSQL_PORT=1433
MSSQL_PASSWORD=mssqlPass1

# Network settings
DATABASE_NETWORK=database_network


```

---

Create network with the name, that we have in `DATABASE_NETWORK` environment variable.

```shell script
docker network create database_network
```

---

Build the Docker image

```shell script
docker-compose build
```


## Running

Start
```
docker-compose up
```

Stop
```
docker-compose down
```

## Usage

- Access **MSSQL** using  `sqlcmd -S localhost -U SA -P '<YourPassword>'` in command line.