FROM python:3.7-alpine3.8

ENV PYTHONUNBUFFERED 1

RUN apk update \
    && apk add libpq postgresql-dev \
    && apk add build-base

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install -r requirements.txt

EXPOSE 8000
CMD ["ash"]
