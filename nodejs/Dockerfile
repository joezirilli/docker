FROM ubuntu

MAINTAINER joe@avenerios.com

# Install node & forever
RUN sudo apt-get update
RUN sudo apt-get install -y curl
RUN curl --silent --location https://deb.nodesource.com/setup_0.12 | sudo bash -
RUN sudo apt-get install -y nodejs
RUN sudo npm install -g forever

# Setup deploy user
RUN sudo useradd --create-home -s /bin/bash deploy
RUN sudo adduser deploy sudo

ONBUILD COPY . /home/deploy/app
ONBUILD RUN chown -R deploy:deploy /home/deploy

ONBUILD USER deploy
ONBUILD WORKDIR /home/deploy/app
ONBUILD RUN npm install

CMD npm start