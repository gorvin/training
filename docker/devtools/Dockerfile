FROM ubuntu:bionic
LABEL maintainer "Igor Vincic <gorvin@users.noreply.github.com>"

ARG APP_LANG="en_US.UTF-8"
ARG APP_LANGUAGE="en_US:en"
ARG APP_LC_ALL="en_US.UTF-8"

ENV DEBIAN_FRONTEND=noninteractive \
    DEBCONF_NONINTERACTIVE_SEEN=true \
    TZ="UTC" \
    TERM=linux

RUN apt-get update -qqy \
    && apt-get install -qqy --no-install-recommends \
        apt-utils \
    && apt-get install -qqy --no-install-recommends \
        locales \
    && locale-gen --purge "${APP_LANG}" \
    && update-locale LANG="${APP_LANG}" LANGUAGE="${APP_LANGUAGE}" LC_ALL="${APP_LC_ALL}" \
    && dpkg-reconfigure --frontend noninteractive locales \
    && apt-get install -qqy --no-install-recommends \
        language-pack-en \
        tzdata \
    && echo "${TZ}" > /etc/timezone \
    && dpkg-reconfigure --frontend noninteractive tzdata \
    && rm -rf /var/lib/{apt,dpkg,cache,log}/ \
        /tmp/* \
        /var/tmp/*

RUN apt-get update -qqy \
    && apt-get install -qqy --no-install-recommends \
        binutils \
        build-essential \
        bzip2 \
        curl \
        ca-certificates \
        git \
        openjdk-8-jre-headless \
        unzip \
        wget \
    && sed -e 's/securerandom\.source=file:\/dev\/random/securerandom\.source=file:\/dev\/urandom/' \
        -i /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/security/java.security \
    && rm -rf /var/lib/{apt,dpkg,cache,log}/ \
        /tmp/* \
        /var/tmp/*

ENV LANG=${APP_LANG} \
    LANGUAGE=${APP_LANGUAGE} \
    LC_ALL=${APP_LC_ALL}

CMD ["bash", "-s"]
