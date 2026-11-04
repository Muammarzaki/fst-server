# FST UIN Project

## Project Structure

- `docker-compose.db.yaml` - Database service configuration
- `docker-compose.app.yaml` - Application services configuration
- `docker-compose.traefik.yaml` - Traefik reverse proxy configuration
- `traefik/` - Traefik configuration files

## Getting Started

1. Create required networks:
    ```bash
    docker network create traefik
    docker network create db-network
    ```

2. Copy `.env.example` to `.env` and configure your environment variables

3. Start the services:
    ```bash
    docker compose -f docker-compose.db.yaml -f docker-compose.app.yaml -f docker-compose.traefik.yaml up -d
    ```

## Services

- Dashboard: https://dashboard.fst.uin.ar-raniry.ac.id
- Profile: https://fst.uin.ar-raniry.ac.id
- News Dashboard: https://news.fst.uin.ar-raniry.ac.id
- News Service: https://api.news.fst.uin.ar-raniry.ac.id

## Maintenance

- Services are automatically updated using Watchtower
- SSL certificates are automatically managed by Let's Encrypt
- Logs are available in `./var/traefik/`

```

These files will:
1. Make the project more maintainable
2. Improve security by moving sensitive data to `.env`
3. Provide documentation for other developers
4. Prevent unnecessary files from being included in Docker builds

After adding these files:
1. Replace hardcoded environment variables in your compose files with references to `.env` variables
2. Update `.gitignore` to exclude `.env` file
3. Make sure all team members have access to the documentation

Would you like me to show how to update any specific part of your existing configuration to work with these new files?