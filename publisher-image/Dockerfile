# base image to build upon
FROM registry.redhat.io/ubi7

# pull in Values_publisher executable from Nexus AND give execute permission to running the pub app
RUN curl -k -u admin:admin --output Values_publisher https://nexus-openshift/repository/executables/Values_publisher \ 
	&& chmod +x ./Values_publisher \
	&& yum install -y glibc.i686 iputils

# select random user
USER 1001
EXPOSE 7400/udp 7410/udp 7411/udp

# when the container runs, run Values_publisher
ENTRYPOINT ./Values_publisher > /tmp/pubout.txt
