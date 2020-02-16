FROM ubuntu:bionic

ENV LANG C.UTF-8
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -yq update \
    && apt-get -yq install --no-install-recommends \
		git \
        gcc \
		libc-dev \
	&& apt-get clean \
	&& rm -rf /tmp/* /var/tmp/* /var/lib/apt/archive/* /var/lib/apt/lists/*

CMD ["bash", "-s"]
