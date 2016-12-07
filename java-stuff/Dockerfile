FROM amazonlinux

ENV JRE_VERSION "jdk1.8.0_112"
ENV JRE_COOKIE "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie"
ENV JRE_TAR_URL "http://download.oracle.com/otn-pub/java/jdk/8u112-b15"
ENV JRE_TAR_FILE "server-jre-8u112-linux-x64.tar.gz"
ENV JRE_INSTALL_PATH "/usr/java"
ENV SOLR_URL "http://www-us.apache.org/dist/lucene/solr/6.3.0/solr-6.3.0-src.tgz"

MAINTAINER afym

# installing JRE in the system

RUN yum clean all && \
    yum -y update && \
    yum -y install wget && \
    mkdir ${JRE_INSTALL_PATH} -p && \
    wget --no-cookies --no-check-certificate --header "${JRE_COOKIE}" -O ${JRE_INSTALL_PATH}/${JRE_TAR_FILE} "${JRE_TAR_URL}/${JRE_TAR_FILE}" && \
    cd ${JRE_INSTALL_PATH} && \
    tar zxvf ${JRE_TAR_FILE} && \
    rm ${JRE_TAR_FILE}

# adding path to the system

ENV PATH="${JRE_INSTALL_PATH}/${JRE_VERSION}/bin:${PATH}"

