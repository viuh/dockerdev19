
FROM ubuntu:18.04
#FROM ruby:2.6.0
FROM node:8.17

RUN echo "Starting installations (rails)"

RUN apt-get update && apt-get install -y git build-essential curl 
RUN apt-get install -y zlib1g-dev libssl-dev libreadline-dev libyaml-dev libxml2-dev libxslt-dev
RUN apt-get clean

RUN git clone https://github.com/rbenv/rbenv.git ~/.rbenv
RUN echo 'export PATH="$HOME/.rbenv/bin:$HOME/.rbenv/shims/:$PATH"' >> ~/.bashrc

ENV PATH /root/.rbenv/bin:$PATH
RUN echo 'eval "$(rbenv init -)"' >> ~/.bashrc
RUN echo 'eval "$(rbenv init -)"' >> /etc/profile.d/rbenv.sh

RUN git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

RUN rbenv install 2.6.0
RUN rbenv global 2.6.0

RUN ls -la /root/.rbenv/bin
RUN ls -la /root/.rbenv/shims

RUN rbenv global 2.6.0 && /root/.rbenv/shims/gem install bundler
RUN rbenv global 2.6.0 && /root/.rbenv/shims/gem install rails

RUN git clone https://github.com/docker-hy/rails-example-project
WORKDIR rails-example-project
#RUN bundle platform --ruby
#RUN bundle update --ruby


RUN /root/.rbenv/shims/bundle install

RUN /root/.rbenv/shims/rails db:migrate


CMD /root/.rbenv/shims/rails db:migrate RAILS_ENV=production
CMD /root/.rbenv/shims/rake assets:precompile

CMD [-e config/master.key] && rm config/master.key
CMD [-e config/credentials.yml.enc] && rm config/credentials.yml.enc

#RUN [-e config/master.key] && rm config/master.key
#RUN [-e config/credentials.yml.enc] && rm config/credentials.yml.enc

#RUN EDITOR="mate --wait" /root/.rbenv/shims/rails credentials:edit 2>&1 > test.log
#CMD EDITOR="mate --wait" /root/.rbenv/shims/rails credentials:edit 2>&1 > prod.log

#RUN /root/.rbenv/shims/rails credentials:edit
#CMD /root/.rbenv/shims/rails credentials:edit > test.log 


ENV RAILS_MASTER_KEY $(cat config/master.key)


#CMD RAILS_LOG_TO_STDOUT=true /root/.rbenv/shims/rails s
#RUN RAILS_LOG_TO_STDOUT=true /root/.rbenv/shims/rails s
CMD RAILS_LOG_TO_STDOUT=true /root/.rbenv/shims/rails s


#CMD RAILS_LOG_TO_STDOUT=true /root/.rbenv/shims/rails s -e production 
#RUN RAILS_LOG_TO_STDOUT=true /root/.rbenv/shims/rails s -e production 

