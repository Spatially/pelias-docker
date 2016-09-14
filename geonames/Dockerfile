FROM node:0.12.13
MAINTAINER Jan Nonnen <helvalius@gmail.com>


ARG OSM=http://download.geofabrik.de/north-america-latest.osm.pbf

# Auxiliary folders
RUN mkdir -p /mnt/data/openstreetmap \
  & mkdir -p /tmp/openstreetmap \
  & mkdir -p /mnt/data/openaddresses \
  & mkdir -p /mnt/data/nls-places



# Download WOF
WORKDIR /mnt/data/
RUN git clone https://github.com/pelias/geonames \
  && cd geonames \
  && npm install \
  && bin/pelias-geonames -m


VOLUME ["/mnt/data/geonames/data"]

COPY docker-entrypoint.sh /

#ENTRYPOINT ["/docker-entrypoint.sh"]
