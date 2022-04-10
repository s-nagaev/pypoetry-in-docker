# Python & Poetry in Docker

**Registry**: [DockerHub](https://hub.docker.com/r/pysergio/pypoetry)


# About

This repository contains dockerfiles based on [official Python Alpine-based docker images](https://hub.docker.com/_/python?tab=tags&page=1&name=alpine) with pre-installed and pre-configured
[Poetry](https://python-poetry.org/) dependency manager, libraries for PostgreSQL database adapter ([psycopg2](https://pypi.org/project/psycopg2/)) and
software to simplify interaction within the application environment.

Thus images from this repository should be easy to use with most of the regular Django projects. 


# How to use this image

## Create a `Dockerfile` in your Python app project

```dockerfile
FROM pysergio/pypoetry:3.9-alpine

WORKDIR /app

COPY pyproject.toml /app/pyproject.toml
COPY poetry.lock /app/poetry.lock

RUN poetry install

COPY . .

CMD [ "python", "./your-daemon-or-script.py" ]
```

Then you can build and run the Docker image:

```console
$ docker build -t my-python-app .
$ docker run -it --rm --name my-running-app my-python-app
```

# License

View license information for [Python 3](https://docs.python.org/3/license.html) and [Poetry](https://github.com/python-poetry/poetry/blob/master/LICENSE). As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).

