FROM ruby

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y nodejs build-essential sqlite3
RUN gem install rails -v '5.1.6'

ONBUILD COPY ruby_app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate && rake db:seed

# To build
# docker build -t ex02 .
