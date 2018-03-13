# COMMENTS:
#	This file describes how is the FCND (Flying Car NanoDegree)
#	Starter Environment created
# USAGE:
#
#	# Build image
#	docker build -t fcnd .
#   
#   # Run the image
#	docker run fcnd
#   # Mount your code in the environment
#   docker run -v $(pwd):/var/www fcnd 
#
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

RUN [ "/bin/bash", "-c", "source activate fcnd" ]

CMD [ "/bin/bash" ]