# CentOS 7 Container with the Oracle Java JRE 8 installed
FROM java-jre:1.8.0_latest

MAINTAINER OpenSource Connections <ops@opensourceconnections.com>

# Expose ports 8983
EXPOSE 8983

# Install the unzip utility
RUN yum install -y unzip && yum clean all

# Download the Solr 5.3.0 tar and extract. Remove docs, examples, and licenses to keep disk usage low
RUN mkdir solr && curl http://apache.mirrors.pair.com/lucene/solr/5.3.0/solr-5.3.0.tgz | tar xzpf - -C solr --strip-components 1 && rm -rf solr/{docs,example,licenses,CHANGES.txt,LICENSE.txt,LUCENE_CHANGES.txt,NOTICE.txt,README.txt}

# Set the amount of memory to use
ENV SOLR_HEAP_MEMORY 1g

# Start Solr
CMD cd /solr && bin/solr start -m $SOLR_HEAP_MEMORY -p 8983 -f
