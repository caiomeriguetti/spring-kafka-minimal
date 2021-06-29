FROM ubuntu

RUN apt-get update
RUN apt-get install -y wget openjdk-8-jdk
RUN wget https://downloads.apache.org/kafka/2.8.0/kafka_2.12-2.8.0.tgz -O kafka.tgz
RUN tar -xzf kafka.tgz
RUN sed -i 's/localhost:2181/zookeeper:2181/' kafka_2.12-2.8.0/config/server.properties
RUN sed -i 's/#advertised\.listeners/advertised\.listeners/' kafka_2.12-2.8.0/config/server.properties
RUN sed -i 's/your\.host\.name/localhost/' kafka_2.12-2.8.0/config/server.properties

RUN apt-get install -y net-tools
WORKDIR kafka_2.12-2.8.0
