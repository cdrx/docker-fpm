FROM centos:5

RUN set -x \
    && yum install -y ruby-devel rubygems gcc make rpmdevtools \
    && gem install json -v 1.8.3 \
    && gem install fpm -v 1.4.0 \
    && yum clean all \
    && mkdir /src

WORKDIR /src/

CMD /usr/local/bin/fpm
