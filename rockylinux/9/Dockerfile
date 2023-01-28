FROM rockylinux:9

RUN set -x \
    && dnf update -y \
    && dnf install -y ruby-devel rubygems gcc make rpmdevtools \
    && gem install fpm \
    && dnf clean all \
    && mkdir /src

WORKDIR /src/

CMD /usr/local/bin/fpm
