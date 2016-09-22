FROM fedora:20

ENV TINI_VERSION v0.10.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN chmod +x /tini

RUN set -x \
    && dnf install -y ruby-devel gcc make rpmdevtools \
    && gem install fpm \
    && dnf clean all \
    && mkdir /src

WORKDIR /src/

ENTRYPOINT ["/tini", "-g",  "--", "/usr/local/bin/fpm"]