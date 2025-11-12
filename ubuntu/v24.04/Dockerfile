# vim:set ft=dockerfile:
FROM ubuntu:24.04

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
  "Types: deb" \
  "URIs: ${REPO_URI}" \
  "Suites: noble noble-updates noble-backports" \
  "Components: main universe restricted multiverse" \
  "Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg" \
  "" \
  "Types: deb" \
  "URIs: ${REPO_URI}" \
  "Suites: noble-security" \
  "Components: main universe restricted multiverse" \
  "Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg" \
  > /etc/apt/sources.list.d/ubuntu.sources && \
  apt-get update && \
  apt-get upgrade -y && \
  apt-get install -y --no-install-recommends tzdata && \
  ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime && \
  rm -rf /var/lib/apt/lists/*

ENV LANG=C.UTF-8

CMD ["/bin/bash"]