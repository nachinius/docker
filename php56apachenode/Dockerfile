FROM php:5.6-apache

MAINTAINER nachinius <ignacio.peixoto@gmail.com>

# disable interactive
ENV DEBIAN_FRONTEND noninteractive

# Configure PHP (CLI and Apache)
RUN php_ini="/usr/local/etc/php/conf.d/date-timezone.conf" && \
    echo "date.timezone = UTC" >> $php_ini


RUN curl -sS https://getcomposer.org/installer | php

ENV NODE_VERSION 0.12.7
ENV NPM_VERSION 2.14.1

# installing node
RUN curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
    && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc" \
    && tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1 \
    && rm "node-v$NODE_VERSION-linux-x64.tar.gz" SHASUMS256.txt.asc \
    && npm install -g npm@"$NPM_VERSION" \
    && npm cache clear
    



