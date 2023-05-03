# GeoHealthCheck for the eMOTIONAL Cities SDI

<img src="https://raw.githubusercontent.com/doublebyte1/yellow-bricks/master/dist/assets/img/portfolio/ecities.svg" width="200">

This repository provides code for deploying a [GeoHealthCheck](https://geohealthcheck.org/) infrastructure. 

## Quick Setup

You will need `docker` and `docker-compose` installed in your system, in order to run this infrastructure. If you don't have them already, you can get it from [here](https://raw.githubusercontent.com/emotional-cities/openapi-sdi/master/install_docker.sh):

```
./install_docker.sh
```

Setup the [environment variables](#environment-variables).

Then run:

```
docker-compose up -d
```

Stop with:

```
docker-compose down
```

If you use the `d` flag with docker-compose down, you will remove the sqlite volume, which contains the probes!


## Environment Variables

This compositions read secrets from an environment file on this folder: ```ghc.env```.

Create this file with the following format, filling the relevant values.

```
SQLALCHEMY_DATABASE_URI=sqlite:////GeoHealthCheck/DB/data.db

# Core variables settings, change at will.
GHC_RUNNER_IN_WEBAPP=False
GHC_NOTIFICATIONS=True
GHC_NOTIFICATIONS_VERBOSITY=True
GHC_ADMIN_EMAIL=
GHC_NOTIFICATIONS_EMAIL=
GHC_SMTP_SERVER=smtp.gmail.com
GHC_SMTP_PORT=587
GHC_SMTP_TLS=True
GHC_SMTP_SSL=False
GHC_SMTP_USERNAME=
GHC_SMTP_PASSWORD=
GHC_LOG_LEVEL=20
GHC_SITE_TITLE=GeoHealthCheck of the eMOTIONAL Cities SDI
GHC_SITE_URL=health.byteroad.net
GHC_SELF_REGISTER=True
GHC_VERIFY_SSL=True
#GHC_REQUIRE_WEBAPP_AUTH=True

# GHC_USER_PLUGINS=GeoHealthCheck.plugins.user.mywmsprobe,GeoHealthCheck.plugins.user.mywmsprobe2

# Optionally set container Timezone
# CONTAINER_TIMEZONE=Europe/London

# Optionally: set language
# LC_ALL=nl_NL.UTF-8
# LANG=nl_NL.UTF-8
# LANGUAGE=nl_NL.UTF-8
```

## License

This project is released under an [MIT License](./LICENSE)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)