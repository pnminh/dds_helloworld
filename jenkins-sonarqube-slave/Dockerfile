FROM registry.redhat.io/openshift4/ose-jenkins-agent-base
ENV SONAR_SCANNER_OPTS "-Djavax.net.ssl.trustStore=/etc/pki/java/cacerts -Djavax.net.ssl.keyStore=/etc/pki/java/cacerts"
RUN yum install unzip make libstdc++ gcc-c++ -y 

WORKDIR /tmp

COPY ./sonar-scanner-cli-4.2.0.1873-linux.zip /tmp
COPY ./build-wrapper-linux-x86.zip /tmp
COPY ./SSLPoke.class /tmp
COPY ./cacerts /etc/pki/java/cacerts

RUN unzip -qq sonar-scanner-cli-4.2.0.1873-linux.zip && \
    rm sonar-scanner-cli-4.2.0.1873-linux.zip && \
    mv sonar-scanner-4.2.0.1873-linux /sonar-scanner && \
    unzip -qq build-wrapper-linux-x86.zip && \
    rm build-wrapper-linux-x86.zip && \
    mv build-wrapper-linux-x86 /sonar-scanner/build-wrapper && \
    ln -s /sonar-scanner/bin/sonar-scanner /usr/bin
