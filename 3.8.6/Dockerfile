from python:3.8.6-alpine

RUN apk update \
    && apk add --no-cache --virtual .build-deps \
    ca-certificates gcc postgresql-dev linux-headers musl-dev \
    libffi-dev jpeg-dev zlib-dev git bash make

RUN pip install --upgrade pip --no-cache-dir \
    && pip install poetry --no-cache-dir

RUN python -m poetry config virtualenvs.create false

