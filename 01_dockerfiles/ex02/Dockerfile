FROM ruby
RUN apt-get update && apt-get install && gem install rails && \
apt-get install nodejs -y

ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install

EXPOSE 3000
CMD ["rails", "s", "-b", "0.0.0.0", "-p" ,"3000"]

ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed
