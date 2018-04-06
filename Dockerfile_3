FROM registry.access.redhat.com/redhat-openjdk-18/openjdk18-openshift:1.3
USER root
RUN yum -y install net-tools
USER jboss
COPY Siemens_RootCA_V30_2016.crt /home/jboss/
