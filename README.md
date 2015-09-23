# Solr Docker

Sample Dockerfiles for running Solr in a docker container. With this approach we have separated the service and configuration into two containers. This allows our team to re-use the base `solr` container across many projects. The configuration for any core(s) happens in a separate `core` container which is layered on the first. Settings are exposed via environment variables which may be overridden in the `core` container.

## Running
1. Build / find a JRE 8 container (update the `solr/Dockerfile` to point at this container)
1. Build the `solr` container
   
   ```bash
   cd solr
   docker build -t solr:5.3.0-1 .
   ```
1. Build the `core` container
   
   ```bash
   cd core
   docker build -t solr-core .
   ```
1. Run the container
   
   ```bash
   docker run -P solr-core
   ```
