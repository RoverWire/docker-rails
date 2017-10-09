FROM ruby:2.0.0

MAINTAINER Luis Perez <luis.felipe@cl.ly>

RUN apt-get update -qq && apt-get install -y build-essential software-properties-common python-software-properties \
    zlib1g-dev libssl-dev libreadline-dev libyaml-dev build-essential libpq-dev \
    libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev libffi-dev \
    wget curl \
    python-dev python-pip \
    nodejs

ENV APP_HOME /app
RUN mkdir -p $APP_HOME
WORKDIR $APP_HOME

COPY engine/Gemfile $APP_HOME
COPY engine/Gemfile.lock $APP_HOME
RUN bundle install

COPY ./engine $APP_HOME
