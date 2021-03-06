# Biblys Cloud Analytics

Privacy-focused web analytics for [Biblys Cloud](https://biblys.cloud) based on Matomo

## Run using Docker

Define database and SMTP credentials in a .env file:

```env
MATOMO_DATABASE_HOST=
MATOMO_DATABASE_PORT=
MATOMO_DATABASE_USERNAME=
MATOMO_DATABASE_PASSWORD=
MATOMO_DATABASE_DBNAME=
MATOMO_MAIL_HOST=
MATOMO_MAIL_PORT=
MATOMO_MAIL_USERNAME=
MATOMO_MAIL_PASSWORD=
MATOMO_MAIL_ENCRYPTION=
MATOMO_GENERAL_FORCE_SSL=
MATOMO_GENERAL_ENABLE_TRUSTED_HOST_CHECK=
```

Then run:

```console
docker run -d -p 3100:80 \
  --env-file=.env \
  --memory=512mb \
  --restart=unless-stopped \
  --name analytics \
  biblys/analytics:3.14.1
```

## Build & push image

```console
docker build -t biblys/analytics:latest -t biblys/analytics:3.14.1 .
docker push biblys/analytics:latest
docker push biblys/analytics:3.14.1
```

## TODO

- docker matomo fpm image?
- docker matomo alpine image?

