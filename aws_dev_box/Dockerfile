FROM centos:latest

LABEL version="0.1.0"
LABEL description="CentOS 8 based AWS developer container"
LABEL maintainer="andrew.hudson@versent.com.au"

# Pre-reqs
RUN yum install -y tar gzip unzip python3

# saml2aws
# execute 'saml2aws login' when inside container
ENV CURRENT_VERSION=2.27.1
RUN curl -L https://github.com/Versent/saml2aws/releases/download/v${CURRENT_VERSION}/saml2aws_${CURRENT_VERSION}_linux_amd64.tar.gz -o saml2aws.tar.gz 
RUN tar -xzvf saml2aws.tar.gz -C /usr/sbin
RUN chmod u+x /usr/sbin/saml2aws
COPY saml2aws /root/.saml2aws
RUN mkdir /root/.aws
COPY config /root/.aws/config

# aws cli
RUN curl -L "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN ./aws/install

# sceptre
RUN pip3 install sceptre
