# Base image
# FROM resin/rpi-raspbian:buster
ARG base
#FROM debian:buster
FROM ${base}

# Maintainer info
MAINTAINER Javier Santacruz <javier.santacruz.lc@gmail.com>

# Install prerequisites
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y python git-core python-openssl python-lxml

# Install CouchPotato
RUN cd /opt && \
  git clone https://github.com/CouchPotato/CouchPotatoServer.git

# Expose port
EXPOSE 5050
VOLUME /config /downloads /torrents

# Run CouchPotato
WORKDIR /opt/CouchPotatoServer
ENTRYPOINT ["python", "CouchPotato.py", "--config_file", "/config/CouchPotato.cfg", "--data_dir", "/config/data", "--console_log"]
