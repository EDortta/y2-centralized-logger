# fluentd/Dockerfile
FROM fluent/fluentd:v1.18-debian-1
USER root
RUN gem install fluent-plugin-elasticsearch --no-document --version 5.3.0
RUN rm -rf /usr/local/bundle/extensions
USER fluent
