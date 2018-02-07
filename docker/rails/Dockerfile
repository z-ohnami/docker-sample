FROM ruby:2.4.3-alpine3.7
MAINTAINER makoto.ohnami<z.ohnami@gmail.com>

ARG RAILS_ENV_ARG
ARG SECRET_KEY_BASE_ARG
ARG BUNDLE_GEMFILE_ARG

ENV RAILS_ENV ${RAILS_ENV_ARG}
ENV SECRET_KEY_BASE ${SECRET_KEY_BASE_ARG}
ENV BUNDLE_GEMFILE ${BUNDLE_GEMFILE_ARG}
# bin/rails's case.not recommend.
ENV RAILS_SERVE_STATIC_FILES true

WORKDIR /app
RUN apk add --no-cache tzdata && \
    apk --no-cache --virtual gem-builddeps add alpine-sdk sqlite-dev ruby-dev musl-dev libffi-dev linux-headers make g++  && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apk update && apk add yarn git sqlite-libs && \
    git clone https://github.com/z-ohnami/omochi.git

WORKDIR /app/omochi

RUN bundle install -j4 --path=.bundle && yarn install && ./bin/webpack && \
    apk del gem-builddeps

ADD . /app

EXPOSE 3000

#ENTRYPOINT ["./bin/rails", "s", "-p", "3000"]
#ENTRYPOINT ["./bin/bundle", "exec", "unicorn", "-p", "3000"]
#CMD ["/app/omochi/bin/bundle", "exec", "unicorn", "-p", "3000", "-c", "/app/omochi/config/unicorn.rb"]

