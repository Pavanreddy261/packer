FROM docker.mirror.hashicorp.services/alpine:latest
LABEL maintainer="The Packer Team <packer@hashicorp.com>"

ENV PACKER_VERSION=1.7.2
ENV PACKER_SHA256SUM=9429c3a6f80b406dbddb9b30a4e468aeac59ab6ae4d09618c8d70c4f4188442e

RUN apk add --update git bash wget openssl

ADD https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip ./
ADD https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_SHA256SUMS ./

RUN sed -i '/.*linux_amd64.zip/!d' packer_${PACKER_VERSION}_SHA256SUMS
RUN sha256sum -cs packer_${PACKER_VERSION}_SHA256SUMS
RUN unzip packer_${PACKER_VERSION}_linux_amd64.zip -d /bin
RUN rm -f packer_${PACKER_VERSION}_linux_amd64.zip

ENTRYPOINT []