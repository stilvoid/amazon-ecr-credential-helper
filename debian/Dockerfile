FROM debian:sid

RUN DEBIAN_FRONTEND=noninteractive apt-get -o Acquire::ForceIPv4=true update && \
    apt-get -o Acquire::ForceIPv4=true install -yq \
      debhelper \
      dh-golang \
      golang-go \
      golang-github-aws-aws-sdk-go-dev \
      golang-github-docker-docker-credential-helpers-dev \
      golang-github-mitchellh-go-homedir-dev \
      golang-github-sirupsen-logrus-dev \
      golang-github-golang-mock-dev

WORKDIR /sources

CMD ["sh", "-c", "dpkg-buildpackage -uc -us && cp ../amazon-ecr-credential-helper_* ."]
