# Solr Docker

Sample Dockerfiles for running Solr in a docker container. With this approach we have separated the service and configuration into two containers. This allows our team to re-use the base `solr` container across many projects. The configuration for any core(s) happens in a separate `core` container which is layered on the first. Settings are exposed via environment variables which may be overridden in the `core` container.
