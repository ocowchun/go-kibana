FROM docker.elastic.co/elasticsearch/elasticsearch-oss:6.0.0

RUN yum install -y epel-release && yum install -y nodejs && \
    npm install -g makelogs

RUN wget -O /usr/local/bin/dumb-init https://github.com/Yelp/dumb-init/releases/download/v1.1.3/dumb-init_1.1.3_amd64 && \
    chmod +x /usr/local/bin/dumb-init

ADD entrypoint.sh /entrypoint.sh
ADD scripts /scripts

ENTRYPOINT ["/entrypoint.sh"]

CMD ["/usr/share/elasticsearch/bin/elasticsearch"]
