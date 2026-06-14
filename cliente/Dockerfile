FROM ubuntu:22.04

RUN apt-get update && apt-get install -y \
    mysql-client \
    && rm -rf /var/lib/apt/lists/*

CMD ["mysql", "--version"]