FROM ruby:2.4.3-alpine3.7
MAINTAINER makoto.ohnami<z.ohnami@gmail.com>

ARG RAILS_ENV_ARG
ARG SECRET_KEY_BASE_ARG
ENV RAILS_ENV ${RAILS_ENV_ARG}
ENV SECRET_KEY_BASE ${SECRET_KEY_BASE_ARG}

WORKDIR /opt
RUN apk add --no-cache tzdata && \
    apk --no-cache --virtual gem-builddeps add alpine-sdk sqlite-dev && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apk update && apk add yarn git && \ 
    git clone https://github.com/z-ohnami/omochi.git

WORKDIR /opt/omochi
RUN bundle install --path=.bundle && yarn install && ./bin/webpack

EXPOSE 3000
ENTRYPOINT ["./bin/rails", "s", "-p", "3000"]

