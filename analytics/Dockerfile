FROM python:3.10-slim-buster

ENV DB_USERNAME=myuser \
    DB_PASSWORD=${POSTGRES_PASSWORD} \
    DB_HOST=127.0.0.1 \
    DB_PORT=5433 \
    DB_NAME=mydatabase \
    POSTGRES_PASSWORD=mypassword

USER root

WORKDIR /src

COPY requirements.txt requirements.txt

RUN apt update -y && apt install -y build-essential libpq-dev 

RUN pip install --upgrade pip setuptools wheel && pip install -r requirements.txt

COPY . analytics

CMD python analytics/app.py  
