
FROM ubuntu:16.04
RUN echo "Starting installations"

RUN apt-get update && apt-get install -y curl git

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash

RUN git clone https://github.com/docker-hy/frontend-example-docker
WORKDIR frontend-example-docker

RUN apt install -y nodejs
RUN node -v && npm -v

RUN echo "Installing packages"
RUN npm install
CMD npm start


#run like this
#docker build -t frontendex .
#docker run -p 5000:5000 frontendex
