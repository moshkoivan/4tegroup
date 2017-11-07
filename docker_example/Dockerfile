FROM ubuntu:14.04
MAINTAINER javacodegeeks

RUN apt-get update && apt-get install -y python-software-properties software-properties-common
RUN add-apt-repository ppa:webupd8team/java

RUN echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 boolean true" | debconf-set-selections

RUN apt-get update && apt-get install -y oracle-java8-installer maven

ADD . /ivan/4tegroup/docker_example/helloworld
RUN cd /ivan/4tegroup/docker_example/helloworld &&  mvn install
CMD ["java", "-cp", "/ivan/4tegroup/docker_example/helloworld/target/helloworld-1.0.jar", "HelloWorld"]
