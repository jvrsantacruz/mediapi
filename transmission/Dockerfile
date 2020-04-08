# Base image
# FROM resin/rpi-raspbian:buster
# FROM debian:buster
ARG base
FROM ${base}

# Maintainer info
MAINTAINER Javier Santacruz <javier.santacruz.lc@gmail.com>

# Install prerequisites
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y transmission-daemon

# Make it read from /config
ADD ./config/systemd.conf \
    /etc/systemd/system/transmission-daemon.service.d/override.conf

EXPOSE 9091 51413
VOLUME /config /incomplete /downloads /torrents

ENTRYPOINT ["/usr/bin/transmission-daemon", "-f", "--log-error"]
CMD ["--config-dir", "/config"]
