FROM ubuntu:bionic
LABEL maintainer "Igor Vincic <gorvin@users.noreply.github.com>"

ARG FOO_VERSION=1

COPY testapp.bin /usr/bin
COPY libfoo.so.${FOO_VERSION} /usr/lib/

RUN ln -sf libfoo.so.${FOO_VERSION} /usr/lib/libfoo.so