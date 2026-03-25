# Getting Started

## Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- A GitHub Token with `repo` permission → https://github.com/settings/tokens

## Steps

### 1. Create a `docker-compose.yml` file

Copy the content below into a new file named `docker-compose.yml` on your machine:

```yaml
services:
  backstage:
    image: ghcr.io/naftiko/backstage:latest
    ports:
      - "7007:7007"
    environment:
      POSTGRES_HOST: postgres
      POSTGRES_PORT: 5432
      POSTGRES_USER: backstage
      POSTGRES_PASSWORD: backstage
      GITHUB_TOKEN: your_token_here  # <-- replace with your GitHub token
    depends_on:
      - postgres

  postgres:
    image: postgres:16
    environment:
      POSTGRES_USER: backstage
      POSTGRES_PASSWORD: backstage
      POSTGRES_DB: backstage
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```

> **💡 Make sure your GitHub Token has the `repo` permission.**

### 2. Start Backstage

```bash
docker compose up
```

### 3. Open http://localhost:7007
