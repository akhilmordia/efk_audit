#docker build --no-cache -t fluentd .

FROM fluent/fluentd:v1.14-debian
USER root
RUN ["gem", "install", "fluent-plugin-elasticsearch", "--version", "5.0.3"]
RUN ["fluent-gem", "install", "fluent-plugin-rewrite-tag-filter"]
RUN ["fluent-gem", "install", "fluent-plugin-multi-format-parser"]
RUN ["fluent-gem", "install", "fluent-plugin-multi-format-parser", "--no-document"]
RUN ["fluent-gem", "install", "fluent-plugin-concat", "--no-document"]
ADD ./conf/fluent.conf /fluentd/etc/fluent.conf