FROM debian:8

ENV TINI_VERSION v0.10.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN chmod +x /tini

ENV DEBIAN_FRONTEND noninteractive

RUN set -x \
	&& apt-get update && apt-get install -y --no-install-recommends \
		ruby \
		ruby-dev \
		gcc \
		make \
		ca-certificates \
		libffi-dev \
		ruby-ffi \
	&& gem install fpm \
	&& mkdir /src/

WORKDIR /src/

ENTRYPOINT ["/tini", "-g",  "--", "/usr/local/bin/fpm"]
