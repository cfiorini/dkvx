FROM ruby:2.6-stretch
RUN apt-get update -qq && apt-get install -y postgresql-client vim curl

RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -

RUN apt-get install -y build-essential nodejs

RUN apt-get install -y gcc g++ make
RUN curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get update && apt-get install -y yarn

RUN gem install rails --prerelease

CMD tail -f /dev/null
#CMD ["bundle", "exec", "rails", "server", "-b", "0.0.0.0", "-p", "80", "-e", "production"]
