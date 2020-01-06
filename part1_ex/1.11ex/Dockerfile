
FROM ubuntu:16.04
RUN echo "Starting installations (backend)"

RUN apt-get update && apt-get install -y curl git

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash

RUN git clone https://github.com/docker-hy/backend-example-docker
WORKDIR backend-example-docker

RUN apt install -y nodejs
RUN node -v && npm -v

RUN echo "Installing packages"
RUN npm install
CMD npm start


#run like this
#docker build -t backendex .
#docker run -v $(pwd)/logs.txt:/backend-example-docker/logs.txt -p 8000:8000 backendex
