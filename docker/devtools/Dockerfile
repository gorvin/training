FROM ubuntu:bionic
LABEL maintainer="Igor Vincic <gorvin@users.noreply.github.com>"

ENV DEBIAN_FRONTEND=noninteractive \
    DEBCONF_NONINTERACTIVE_SEEN=true \
    TERM=linux \
	LANG=C.UTF-8 \
    LANGUAGE=C \
    LC_ALL=C.UTF-8

RUN apt-get update -qy \
    && apt-get install -qy --no-install-recommends \
	curl


RUN apt-get update -qy \
    && apt-get install -qy --no-install-recommends \
        binutils \
        build-essential \
        bzip2 \
        curl \
        ca-certificates \
        git \
        patchelf \
        unzip \
        wget \
    && rm -rf /var/lib/{apt,dpkg,cache,log}/ \
        /tmp/* \
        /var/tmp/*

CMD ["bash", "-s"]
