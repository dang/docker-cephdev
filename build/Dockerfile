FROM ubuntu:trusty

MAINTAINER Ivo Jimenez <ivo.jimenez@gmail.com>

RUN apt-get update && \
    apt-get install -y wget && \
    wget https://raw.githubusercontent.com/ceph/ceph/master/install-deps.sh && \
    wget https://raw.githubusercontent.com/ceph/ceph/master/debian/control && \
    mkdir debian && mv control debian && \
    apt-get install -y git && \
    chmod 755 install-deps.sh && \
    ./install-deps.sh && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* debian/
ADD build /
RUN chmod 755 /build
ENTRYPOINT ["/build"]
