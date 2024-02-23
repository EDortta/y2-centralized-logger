# README

This project can help you to start using a centralized logging solution for your Docker projects.

## Simplicity

This project is currently in the initial stage of development, and security features have been disabled for simplicity and ease of setup. Please note that in a production environment, it is crucial to enable and configure security features, including the use of SSL to ensure encrypted communication between services.

## Getting started

To integrate this centralized logging solution with another Docker project, you should configure your services to use Fluentd as the log driver by adding the `--log-driver=fluentd` parameter to your Docker run command or service definition in `docker-compose.yml`. This will direct the logs to the Fluentd service, which can then process and forward them to Elasticsearch.

Here are examples of how to configure your services in `docker-compose.yml` to use Fluentd as the log driver:

```yaml
# Example service using Fluentd log driver
services:
  your_service:
    image: your_image
    logging:
      driver: fluentd
      options:
        fluentd-address: localhost:24224
        tag: docker.{{.Name}}
