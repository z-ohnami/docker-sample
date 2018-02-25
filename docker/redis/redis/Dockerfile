FROM redis:4.0.8-alpine

# install java
#ENV LANG C.UTF-8
#ENV JAVA_HOME /usr/lib/jvm/java-1.7-openjdk/jre
#ENV PATH $PATH:/usr/lib/jvm/java-1.7-openjdk/jre/bin:/usr/lib/jvm/java-1.7-openjdk/bin
#ENV JAVA_VERSION 7u151
#ENV JAVA_ALPINE_VERSION 7.151.2.6.11-r0

#RUN { \
#    echo '#!/bin/sh'; \
#    echo 'set -e'; \
#    echo; \
#    echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; \
#  } > /usr/local/bin/docker-java-home \
#  && chmod +x /usr/local/bin/docker-java-home

#RUN set -x \
#  && apk update \
#  && apk add --no-cache openjdk7-jre="$JAVA_ALPINE_VERSION" \
#  && [ "$JAVA_HOME" = "$(docker-java-home)" ]

# install embulk
#ADD Gemfile Gemfile
#RUN apk add curl \
# && curl --create-dirs -o /usr/local/bin/embulk -L "https://dl.bintray.com/embulk/maven/embulk-0.8.9.jar" \
# && chmod +x /usr/local/bin/embulk
# && embulk bundle install --path=.bundle

# setup data load batch via embulk
# ADD setup.sh setup.sh
# ADD config.yml.liquid config.yml.liquid
# ADD input.json input.json

# RUN chmod +x setup.sh
# CMD ['./setup.sh']
