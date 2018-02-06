FROM nginx:alpine

ENV LANG ja_JP.UTF-8
ENV LC_TIME C
ADD ./docker/nginx/nginx.conf /etc/nginx/nginx.conf
ADD ./docker/nginx/rails.conf /etc/nginx/conf.d/default.conf
