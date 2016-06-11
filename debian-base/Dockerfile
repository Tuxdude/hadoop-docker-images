# A Base Ubuntu image suitable for general development
FROM debian:jessie-backports
MAINTAINER Ash <tuxdude.io@gmail.com>

# Install a base set of packages which we will use
RUN export DEBIAN_FRONTEND=noninteractive && \
    apt-get -y update && \
    apt-get -y --no-install-recommends install \
    apt-utils \
    build-essential \
    supervisor \
    locales \
    git \
    tar \
    vim-nox \
    wget \
    curl \
    dnsutils \
    netcat \
    traceroute \
    net-tools \
    nmap \
    openjdk-8-jdk \
    && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Set UTF-8 locale
RUN export DEBIAN_FRONTEND=noninteractive && \
    dpkg-reconfigure locales && \
    locale-gen C.UTF-8 && \
    /usr/sbin/update-locale LANG=C.UTF-8
ENV LC_ALL C.UTF-8

# Set JAVA_HOME
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

# Optional Golang
#RUN export GOLANG_VERSION="1.5.1" && \
#    export GOLANG_DOWNLOAD_URL="https://golang.org/dl/go$GOLANG_VERSION.linux-amd64.tar.gz" && \
#    export GOLANG_DOWNLOAD_SHA1="46eecd290d8803887dec718c691cc243f2175fe0" && \
#    curl -fsSL "$GOLANG_DOWNLOAD_URL" -o golang.tar.gz \
#    && echo "$GOLANG_DOWNLOAD_SHA1  golang.tar.gz" | sha1sum -c - \
#    && tar -C /usr/local -xzf golang.tar.gz \
#    && rm golang.tar.gz
# ENV PATH /usr/local/go/bin:$PATH

CMD ["/bin/bash"]
