FROM okmillet/centos7:latest
ADD jdk-8u281-linux-x64.tar.gz /usr/local/

RUN mv /usr/local/jdk1.8.0_281 /usr/local/java \
    && rm -f /usr/local/java/*.zip

ENV JAVA_HOME /usr/local/java
ENV PATH $JAVA_HOME/bin:$PATH