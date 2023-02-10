FROM ubuntu:18.04

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends tzdata curl ca-certificates fontconfig locales \
    && echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen \
    && locale-gen en_US.UTF-8 \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y wget libgtk2.0-0 libnss3 libatk-bridge2.0-0

RUN apt install libxshmfence1 libglu1 libasound2-dev -y

RUN wget https://dl.pstmn.io/download/latest/linux64 -O /tmp/postman.tar.gz  && \
    tar -xf /tmp/postman.tar.gz -C /opt && \
    rm /tmp/postman.tar.gz

RUN apt-get install libgtk-3-dev -y
RUN ln -s /opt/Postman/app/postman /bin/postman