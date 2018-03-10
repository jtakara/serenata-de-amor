FROM continuumio/miniconda3:4.3.27p0
MAINTAINER Serenata de Amor "datasciencebr@gmail.com"

USER root
ARG AMAZON_BUCKET
ARG AMAZON_REGION

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        unzip \
        libxml2-dev \
        libxslt-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /mnt/code

COPY ./requirements.txt ./requirements.txt
COPY ./setup ./setup

RUN pip install -r requirements.txt
RUN ./setup
