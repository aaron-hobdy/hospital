FROM openjdk:8

WORKDIR /root

RUN apt-get update && \
    apt-get install -y software-properties-common build-essential git maven

RUN git clone https://github.com/bioinformatics-ua/dicoogle
RUN (cd dicoogle && mvn install && ln -s /root/dicoogle/dicoogle/target/dicoogle.jar /root/)

COPY ./images /tmp
COPY lucene.jar Plugins/lucene.jar
COPY filestorage.jar Plugins/filestorage.jar

EXPOSE 8080
EXPOSE 6666
EXPOSE 1045

CMD ["java", "-jar", "dicoogle.jar", "-s"]

