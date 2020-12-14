FROM amazon/aws-cli:latest

ENV CURRENT_VERSION=2.27.1
RUN yum install -y tar gzip
RUN curl -L https://github.com/Versent/saml2aws/releases/download/v${CURRENT_VERSION}/saml2aws_${CURRENT_VERSION}_linux_amd64.tar.gz -o saml2aws.tar.gz 
RUN tar -xzvf saml2aws.tar.gz -C /usr/sbin
RUN chmod u+x /usr/sbin/saml2aws
COPY saml2aws /root/.saml2aws
RUN mkdir /root/.aws
COPY config /root/.aws/config

# execute 'saml2aws login' when inside container
