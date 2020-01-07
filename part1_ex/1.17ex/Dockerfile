
FROM ubuntu:16.04

RUN apt-get update && apt-get -y install python3 python3-pip git curl wget libglib2.0-0 build-essential libsm6 libxext6 libxrender-dev

RUN pip3 install lxml
RUN pip3 install opencv-python

RUN wget -q https://github.com/milq/milq/blob/master/scripts/bash/install-opencv.sh | bash


CMD echo "Environment version:" && python3 --version 
RUN mkdir -p work/data

WORKDIR work

ENV PS1='$(pwd)> '
RUN export PS1='$(pwd): '

RUN touch README.md
RUN touch prog.py


CMD date
ENTRYPOINT /bin/sh


#docker run -it ownenv


