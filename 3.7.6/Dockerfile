from python:3.7.6-alpine

RUN apk update \
    && apk add --no-cache --virtual .build-deps \
    ca-certificates gcc postgresql-dev linux-headers musl-dev \
    libffi-dev jpeg-dev zlib-dev git bash make curl

RUN pip install --upgrade pip --no-cache-dir

RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python

ENV PATH /root/.poetry/bin:$PATH

RUN poetry config virtualenvs.create false
