FROM fluent/fluentd:latest
MAINTAINER Rowan Carr
USER root
WORKDIR /home/fluent
ENV PATH /home/fluent/.gem/ruby/2.2.0/bin:$PATH
RUN gem install fluent-plugin-secure-forward fluent-plugin-parser fluent-plugin-elasticsearch fluent-plugin-docker-metrics fluent-plugin-nostat
COPY fluent.conf /fluentd/etc/fluent.conf
EXPOSE 24224
CMD fluentd -c /fluentd/etc/$FLUENTD_CONF -p /fluentd/plugins $FLUENTD_OPT
