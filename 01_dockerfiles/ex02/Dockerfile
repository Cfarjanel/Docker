FROM ruby
RUN apt-get update && apt-get install && gem install rails && \
apt-get install nodejs -y && apt-get install -y build-essential libpq-dev

# ONBUILD : executed after the use of the image
ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app

# Install gems files and rails
ONBUILD RUN bundle install
ONBUILD RUN gem install rails

EXPOSE 3000

# Migrate and seed population db
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed

CMD rails s -b 0.0.0.0
