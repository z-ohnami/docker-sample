FROM ruby:2.4.3
MAINTAINER makoto.ohnami<z.ohnami@gmail.com>

WORKDIR /opt
RUN git clone https://github.com/z-ohnami/omochi.git
WORKDIR /opt/omochi
RUN bundle install 
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get install -y apt-transport-https
RUN apt-get update && apt-get install yarn
RUN yarn install

EXPOSE 3000
ENTRYPOINT ["RAILS_ENV=production", "./bin/rails", "s", "-p", "3000"]

