🧱 Common infrastructure components in a single command.

### Observability

| Component | Description |
| --- | --- |
| `./db1-stack elk`| Kibana (http://localhost:5601) |

## Commands

| Command | Description |
| --- | --- |
| `./db1-stack ls` or `db1-stack ps` | List running containers |
| `./db1-stack path` | Display where Stack is located |

## Getting started

### Changing ports

Whether to avoid conflicts or to set a port number that fits best for your enviroment, you can create a `.env` file at `stack path` and change port numbers based on `.env.dist`.

### Install

Just clone this repository:
```shell
git clone https://github.com/db1group/db1-stack
cd db1-stack
```

### Usage
You can use the built-in Shell Script helper:
```shell
./db1-stack <component> <docker compose command>
```

The `<docker compose command>` defaults to `up -d`, so:
```shell
./db1-stack mysql
```
Will be the same as:
```shell
./db1-stack mysql up -d
```
Which does a:
```shell
docker-compose -d mysql/docker-compose.yml up -d
```
Behind the scenes.

#### Which means you can combine any other valid Docker Compose command

Like:
```shell
./db1-stack mysql down
```

Or:
```shell
./db1-stack mysql logs -f
```

---