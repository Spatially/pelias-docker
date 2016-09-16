FROM elasticsearch:1.7
MAINTAINER Jan Nonnen <helvalius@gmail.com>

# Finalize elasticsearch installation
ADD config/elasticsearch.yml /usr/share/elasticsearch/config/

RUN mkdir -p /var/lib/elasticsearch/pelias_data \
  && chown -R elasticsearch:elasticsearch /var/lib/elasticsearch/pelias_data

# https://github.com/elastic/elasticsearch-analysis-icu
RUN /usr/share/elasticsearch/bin/plugin install elasticsearch/elasticsearch-analysis-icu/2.7

ENV ES_HEAP_SIZE 4g
