````md
# pgBackRest Lab

Simple PostgreSQL + pgBackRest lab using Docker Compose.

## Services

- PostgreSQL 16
- pgBackRest
- WAL Archiving

## Features

- Full backups
- Incremental backups
- Restore testing
- WAL archive testing
- Persistent backup repository

---

## Start Services

```bash
docker compose up -d
````

---

## Enter pgBackRest Container

```bash
docker exec -it pgbackrest bash
```

---

## Create Stanza

```bash
pgbackrest --stanza=test stanza-create
```

---

## Create Full Backup

```bash
pgbackrest --stanza=test --type=full backup
```

---

## Create Incremental Backup

```bash
pgbackrest --stanza=test --type=incr backup
```

---

## Show Backup Information

```bash
pgbackrest info
```

---

## Project Structure

```
pgbackrest-lab/
│
├── docker-compose.yml
├── README.md
│
├── pgbackrest/
│   └── pgbackrest.conf
│
├── backups/
│   ├── archive/
│   └── repo/
```

---

## Notes

* Backups are stored outside containers using mounted volumes.
* WAL archiving is enabled.
* Repository persists even if containers are removed.
* This lab is for learning PostgreSQL backup & restore with pgBackRest.

```
```
