# AWS dev box
CentOS 8 based container with saml2aws, AWS CLI and sceptre binaries.

Make sure you update the [saml2aws](./saml2aws) file with your username before building.

## How to build
`docker build . -t aws_dev_box`

## How to run
1. `docker run -it --rm --entrypoint=bash -v /your/local/code/dir:/code/ aws_dev_box`
1. Login to AWS using your ping creds by running `saml2aws login` before using sceptre or AWS CLI.
