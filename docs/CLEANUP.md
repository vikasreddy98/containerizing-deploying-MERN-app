# Cleanup Guide

This guide removes all resources created during the project.

## Stop Docker Compose Stack

```bash
docker compose down
```

---

## View Running Containers

```bash
docker ps
```

View all containers:

```bash
docker ps -a
```

---

## Stop Containers

```bash
docker stop frontend
docker stop backend
docker stop mongodb
```

Or stop all running containers:

```bash
docker stop $(docker ps -q)
```

---

## Remove Containers

```bash
docker rm frontend backend mongodb
```

Or:

```bash
docker rm -f $(docker ps -aq)
```

---

## Remove Images

```bash
docker image ls
```

```bash
docker rmi mern-frontend
docker rmi mern-backend
```

---

## Remove Network

```bash
docker network rm mern
```

---

## Remove Volume

```bash
docker volume ls
```

```bash
docker volume rm mongo-data
```

---

## Full Cleanup

Remove unused resources:

```bash
docker system prune -a
```

Remove unused volumes:

```bash
docker volume prune
```

---

## Verify Cleanup

```bash
docker ps -a
docker image ls
docker network ls
docker volume ls
```

No project resources should remain after cleanup.

