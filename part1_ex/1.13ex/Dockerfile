
FROM ubuntu:16.04
FROM openjdk:8
RUN echo "Starting installations (java spring)"


RUN apt-get update && apt-get install -y  git

RUN git clone https://github.com/docker-hy/spring-example-project
ENV JAVA_HOME=/usr/local/openjdk-8
WORKDIR spring-example-project

RUN chmod u+x ./mvnw
RUN ./mvnw package
#CMD ["/bin/bash"]

CMD java -jar ./target/docker-example-1.1.3.jar

