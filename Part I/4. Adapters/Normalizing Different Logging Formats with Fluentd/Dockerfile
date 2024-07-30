FROM fluent/fluentd:v1.14-1

USER root
# Install the plugin from GitHub repository
RUN fluent-gem install fluent-plugin-redis-slowlog --source https://github.com/mominosin/fluent-plugin-redis-slowlog.git
USER fluent
