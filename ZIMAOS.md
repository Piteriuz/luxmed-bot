# ZimaOS test deployment

This branch contains a ZimaOS/CasaOS test package for the fork. These files are only for self-hosted testing and should be left out of the upstream pull request.

## App Store install

1. Push this branch to GitHub.
2. Let the `Docker` workflow finish successfully. It publishes `ghcr.io/piteriuz/luxmed-bot:latest`.
3. In ZimaOS, add this repository as a custom app store.
4. Install `Luxmed Bot`.
5. Before starting the app, set:
   - `TELEGRAM_TOKEN`
   - `SECURITY_SECRET`
   - `SPRING_DATASOURCE_PASSWORD`
   - `POSTGRES_PASSWORD`
6. `SPRING_DATASOURCE_PASSWORD` and `POSTGRES_PASSWORD` must be identical.

## Direct compose install

Use `docker/docker-compose-ghcr.yml` with a local `secrets.env` based on `docker/secrets.env.template`.

## Notes

- Keep PostgreSQL on `10.6` when reusing an existing database volume.
- Do not expose PostgreSQL ports unless you need external database access.
- The bot has no web UI. Use Telegram and send `/start`.
