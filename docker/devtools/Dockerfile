FROM ubuntu:bionic
LABEL maintainer "Igor Vincic <gorvin@github.com>"

ENV LANG C.UTF-8
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -yq update \
    && apt-get -yq install --no-install-recommends \
        ca-certificates \
        git \
        gcc \
        libc-dev \
        patchelf \
    && apt-get clean \
    && rm -rf /tmp/* /var/tmp/* /var/lib/apt/archive/* /var/lib/apt/lists/*

CMD ["bash", "-s"]
