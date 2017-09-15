FROM ubuntu:16.04

LABEL maintainer="paulo.pacheco@softplan.com.br"

RUN apt-get update && \
    apt-get install -y wget && \
    apt-get install -y tar

RUN wget --no-check-certificate https://github.com/openshift/origin/releases/download/v1.5.1/openshift-origin-client-tools-v1.5.1-7b451fc-linux-64bit.tar.gz
RUN tar -xzf openshift-origin-client-tools-v1.5.1-7b451fc-linux-64bit.tar.gz
RUN ln -s /openshift-origin-client-tools-v1.5.1-7b451fc-linux-64bit/oc /bin/oc

