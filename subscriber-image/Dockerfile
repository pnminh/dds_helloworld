# base image to build upon
FROM nexus-registry-cicd.apps.mario.factory.local/base-image

# pull in Values_publisher executable from Nexus AND give execute permission to running the pub app
RUN curl -k -u admin:admin --output Values_subscriber https://nexus-cicd.apps.mario.factory.local/repository/executables/Values_subscriber \ 
	&& chmod +x ./Values_subscriber \
	&& yum install -y glibc.i686 iputils 
	#&& touch subout.txt \
	#&& chmod 777 subout.txt

# select random user
USER 1001

# expose ports
EXPOSE 7400/udp 7410/udp 7411/udp

# when the container runs, run Values_publisher
ENTRYPOINT ./Values_subscriber > /tmp/subout.txt
