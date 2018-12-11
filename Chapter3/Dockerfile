FROM ruby:2.5.1

ENV LANG C.UTF-8

RUN apt-get update -qq && apt-get install -y --no-install-recommends \
        build-essential \
        libpq-dev \
        nodejs \
        mysql-client \
        vim

WORKDIR /taskleaf
RUN gem install bundler
ADD Gemfile .
ADD Gemfile.lock .
RUN bundle install --jobs=4
ADD . /taskleaf

