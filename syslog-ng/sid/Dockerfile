# Version: 3.13.2

FROM debian:sid-slim

MAINTAINER Carlos Sanz <carlos.sanzpenas@gmail.com>

LABEL vendor=Personal \ 
      com.example.is-beta= \
      com.example.is-production="" \
      com.example.version="3.13.2" \
      com.example.release-date="2016-11-30"

RUN apt-get update -qq && \
    apt-get dist-upgrade -y -qq && \
    apt-get install -y syslog-ng && \
    apt-get autoremove -y -qq && \
    apt-get autoclean -y -qq && \
    rm -rf /var/lib/apt/lists/* 

ADD https://raw.githubusercontent.com/sanzcarlos/syslog-ng/master/syslog-ng/syslog-ng.debian.conf /etc/syslog-ng/syslog-ng.conf

EXPOSE 514/udp
EXPOSE 601/tcp
# EXPOSE 6514/tcp

ENTRYPOINT ["/usr/sbin/syslog-ng", "-F"]