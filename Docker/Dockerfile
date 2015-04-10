#
# WSO2 ESB 4.8.1
#
FROM azul/zulu-openjdk:8
MAINTAINER Totto (totto@totto.org)

RUN apt-get -qq update \
    && apt-get -yqq install ca-certificates ssl-cert wget

# copy zip from local folder to container
RUN wget -P /opt https://s3-us-west-2.amazonaws.com/wso2-stratos/wso2esb-4.8.1.zip && \
    apt-get update && \
    apt-get install -y zip && \
    apt-get clean && \
    unzip /opt/wso2esb-4.8.1.zip -d /opt && \
    rm /opt/wso2esb-4.8.1.zip

ENV JAVA_HOME /usr/lib/jvm/zulu-8-amd64/
#/usr/lib/jvm/java-7-openjdk-amd64
EXPOSE 9443
CMD ["/opt/wso2esb-4.8.1/bin/wso2server.sh"]
