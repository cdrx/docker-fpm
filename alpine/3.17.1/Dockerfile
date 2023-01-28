FROM alpine:3.17.1

RUN set -x \
    && apk add --update --no-cache ruby-dev gcc make \
    && gem install fpm \
    && mkdir /src

WORKDIR /src/

CMD /usr/local/bin/fpm
