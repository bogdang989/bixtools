FROM alpine:3.6
MAINTAINER Yuankun Zhu (zhuy@email.chop.edu)

ENV PICARD_VERSION 2.17.4

RUN apk add --update --no-cache openjdk8-jre ca-certificates wget libc6-compat; \
wget -q https://github.com/broadinstitute/picard/releases/download/${PICARD_VERSION}/picard.jar; \
apk del ca-certificates wget
