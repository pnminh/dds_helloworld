# Dockerfile for RTI DDS HelloWorld

# pull jenkins agent base image
FROM default-route-openshift-image-registry.apps.mario.factory.local/cicd/ose-jenkins-agent-base

# copy RTI DDS framework
COPY ./rti/rti_connext_dds-5.3.1 /opt/rti_connext_dds

# set up the DDS execution environment
ENV NDDSHOME /opt/rti_connext_dds
ENV PATH $PATH:$NDDSHOME/bin

# install dev tools - gcc, make, etc.
# RUN yum groupinstall "Development Tools"
RUN yum update && yum install -y gcc gcc-c++ kernel-devel make glibc-devel.i686 libgcc.i686 libstdc++-devel.i686 ncurses-devel.i686
