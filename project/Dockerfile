# Dockerfile
 
 FROM ubuntu
 RUN apt-get update
 
 # RUBY
 RUN apt-get install -y -q git ruby1.9.1 ruby1.9.1-dev rubygems1.9.1 irb1.9.1 build-essential libopenssl-ruby1.9.1 libssl-dev zlib1g-dev
 
 # RAILS
 RUN gem install rails --no-ri --no-rdoc
 
 # SQLite
 RUN apt-get install -y sqlite3 libsqlite3-dev libyaml-dev libreadline-dev libxml2-dev libxslt1-dev
 ADD . /project
 RUN cd /project;bundle install
 EXPOSE 3000
 
 CMD ["/usr/local/bin/foreman", "start", "-d", "/project"]