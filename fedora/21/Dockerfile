FROM fedora:21

RUN set -x \
    && yum install -y ruby-devel gcc make rpmdevtools \
    && gem install fpm \
    && yum clean all \
    && mkdir /src

WORKDIR /src/

CMD /usr/local/bin/fpm
