ARG FLUENTD_VERSION="1.16.6"
FROM fluentd:v${FLUENTD_VERSION}-1.0

USER root

RUN gem install fluent-plugin-opensearch:1.1.5 && \
    fluent-gem install fluent-plugin-rewrite-tag-filter fluent-plugin-multi-format-parser

USER fluent
ENTRYPOINT ["tini",  "--", "/bin/entrypoint.sh"]
CMD ["fluentd"]