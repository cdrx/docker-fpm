FROM fedora:37

RUN set -x \
    && dnf update -y \
    && dnf install -y ruby-devel gcc make rpmdevtools \
    && gem install fpm \
    && dnf clean all \
    && mkdir /src

WORKDIR /src/

CMD /usr/local/bin/fpm
