FROM centos:5

ENV TINI_VERSION v0.10.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN chmod +x /tini

RUN set -x \
    && yum install -y ruby-devel rubygems gcc make rpmdevtools \
    && gem install fpm -v 1.4.0 \
    && yum clean all \
    && mkdir /src

WORKDIR /src/

ENTRYPOINT ["/tini", "-g",  "--", "/usr/local/bin/fpm"]
