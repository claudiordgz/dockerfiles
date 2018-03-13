FROM continuumio/miniconda3:4.4.10
LABEL maintainer "claudiordgz <claudio.rdgz@gmail.com>"
LABEL description "Miniconda Environment Setup for FCND"

RUN \
    apt-get update \ 
    && apt-get install build-essential software-properties-common -y

ADD ./environment.yml /var/www/environment.yml
WORKDIR  /var/www

RUN [ "conda", "update", "-n", "base", "conda" ]

RUN [ "conda", "env", "create", "-f", "environment.yml" ]

ENTRYPOINT [ "/bin/bash", "-c", "source activate fcnd" ]