FROM docker.elastic.co/elasticsearch/elasticsearch:6.2.2
# FROM elasticsearch:5.6.7

RUN sysctl -w vm.max_map_count=262144 \
 && elasticsearch-plugin install analysis-kuromoji

EXPOSE 9200 9300
