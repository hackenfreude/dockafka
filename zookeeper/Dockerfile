FROM debian:latest

RUN apt-get update && apt-get install -y wget openjdk-7-jre-headless

RUN wget -q -O - http://apache.mirrors.lucidnetworks.net/zookeeper/stable/zookeeper-3.4.6.tar.gz | tar -xzf - -C /opt && mv /opt/zookeeper-3.4.6 /opt/zookeeper && cp /opt/zookeeper/conf/zoo_sample.cfg /opt/zookeeper/conf/zoo.cfg && mkdir -p /tmp/zookeeper

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

EXPOSE 2181

WORKDIR /opt/zookeeper

ENTRYPOINT ["/opt/zookeeper/bin/zkServer.sh"]

CMD ["start-foreground"]
