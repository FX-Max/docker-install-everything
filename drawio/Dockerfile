FROM frekele/ant:1.10.3-jdk8 as BUILD
RUN apt-get update && \
    apt-get install git -y && \
    mkdir /usr/build && \
    git clone https://github.com/jgraph/drawio.git && \
    mv drawio/* /usr/build/ && \
    cd /usr/build/etc/build/ && \
    ant war

FROM tomcat:9.0 as TARGET
COPY --from=BUILD /usr/build/build/draw.war /usr/local/tomcat/webapps/
EXPOSE 8080
CMD ["catalina.sh", "run"]