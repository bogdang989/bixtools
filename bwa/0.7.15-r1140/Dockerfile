FROM alpine:3.6
MAINTAINER Yuankun Zhu (zhuy@email.chop.edu)

ENV BWA_VERSION 0.7.15

RUN apk add --no-cache build-base zlib-dev bzip2-dev ca-certificates wget; \
wget -q https://github.com/lh3/bwa/releases/download/v${BWA_VERSION}/bwa-${BWA_VERSION}.tar.bz2; \
tar xjf bwa-${BWA_VERSION}.tar.bz2; \
cd /bwa-${BWA_VERSION}/ \
&& sed -i '2i#include <stdint.h>' kthread.c \
&& sed -ibak 's/u_int32_t/uint32_t/g' `grep -l u_int32_t *.c *.h` \
&& make; \
mv /bwa-${BWA_VERSION}/bwa /bin/ \
&& rm -rf /bwa-${BWA_VERSION}* \
&& apk del build-base zlib-dev bzip2-dev ca-certificates wget;
