# vim:set ft=dockerfile:
FROM ubuntu:22.04

LABEL maintainer="RegistryHJ (https://github.com/RegistryHJ)"

ARG TARGETARCH
ARG DEBIAN_FRONTEND=noninteractive

RUN \
  set -eux; \
  apt-get update && \
  apt-get install -y --no-install-recommends ca-certificates && \
  REPO_URI="https://ftp.kaist.ac.kr/ubuntu-ports"; \
  if [ "${TARGETARCH}" = "amd64" ]; then \
    REPO_URI="https://ftp.kaist.ac.kr/ubuntu"; \
  fi; \
  printf "%s\n" \
  "deb ${REPO_URI} jammy main universe restricted multiverse" \
  "deb ${REPO_URI} jammy-updates main universe restricted multiverse" \
  "deb ${REPO_URI} jammy-backports main universe restricted multiverse" \
  "deb ${REPO_URI} jammy-security main universe restricted multiverse" \
  > /etc/apt/sources.list && \
  apt-get update && \
  apt-get upgrade -y && \
  apt-get install -y --no-install-recommends tzdata && \
  ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime && \
  rm -rf /var/lib/apt/lists/*

ENV LANG=C.UTF-8

CMD ["/bin/bash"]