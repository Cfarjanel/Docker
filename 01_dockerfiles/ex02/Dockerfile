# docker build -t ft-rails:on-build .
# docker run -d -p 80:3000 --name ex02 --restart=always railsapp
# docker rm -f ex02 && docker rmi ft-rails:on-build && docker rmi railsapp

FROM ruby:2.4

RUN apt-get update && apt-get install -y sqlite3 \
nodejs \
git \
build-essential \
libpq-dev \
postgresql-client \
postgresql \
libxslt1-dev \
libqt4-dev \
xvfb \
redis-server

RUN mkdir -p /opt/app
WORKDIR /opt/app

COPY Gemfile* /opt/app
RUN bundle install

COPY . .

RUN rails new /opt/app
