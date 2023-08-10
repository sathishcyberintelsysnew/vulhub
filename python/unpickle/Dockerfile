FROM python:3.12.0b4-slim

LABEL maintainer="phithon <root@leavesongs.com>"

COPY requirements.txt /tmp/requirements.txt

RUN mkdir /app \
    && pip install -U -r /tmp/requirements.txt

EXPOSE 8000

WORKDIR /app

ENTRYPOINT ["gunicorn"]