FROM okmillet/jdk8:latest
ADD apache-tomcat-8.5.61.tar.gz /usr/local/

RUN mv /usr/local/apache-tomcat-8.5.61 /usr/local/tomcat

ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
WORKDIR $CATALINA_HOME

RUN set -eux; \
    \
    rm -f bin/*.bat; \
    rm -rf webapps/*; \
    for i in `ls`; { if [ -f $i ];then rm -f $i;fi;}; \
    cd conf; \
    sed -i '/<!--/,/-->/d' server.xml; \
    sed -i '/^[[:space:]]*$/d' server.xml; \
    sed -i 's/HTTP\/1.1/org.apache.coyote.http11.Http11Nio2Protocol/' server.xml

EXPOSE 8080
CMD ["catalina.sh", "run"]