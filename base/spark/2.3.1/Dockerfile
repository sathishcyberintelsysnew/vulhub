FROM openjdk:21-ea-13-jdk-slim

ARG basedir=/usr/local/spark

RUN set -ex \
    && apt-get update \
    && apt-get install --no-install-recommends -y procps \
    && mkdir $basedir \
    && wget -qO- https://archive.apache.org/dist/spark/spark-2.3.1/spark-2.3.1-bin-hadoop2.7.tgz | tar zx -C $basedir --strip-components=1 \
    && rm -rf /var/lib/apt/lists/*

WORKDIR $basedir
EXPOSE 8080 7077 6066
COPY docker-entrypoint.sh /docker-entrypoint.sh

ENTRYPOINT [ "/docker-entrypoint.sh" ]

CMD [ "master" ]
