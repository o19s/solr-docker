# Container built from solr/Dockerfile
FROM solr:5.3.0-1

MAINTAINER OpenSource Connections <ops@opensourceconnections.com>

# Override the HEAP setting
ENV SOLR_HEAP_MEMORY 512m

# Copy in the core directory
COPY statedecoded /solr/server/solr/statedecoded
