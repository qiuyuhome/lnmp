FROM alpine:latest

ARG VERSION=4.0.8

ARG REDIS_URL=raw.githubusercontent.com/antirez/redis

RUN wget https://${REDIS_URL}/${VERSION}/src/redis-trib.rb -O /usr/bin/redis-trib.rb \
    && chmod +x /usr/bin/redis-trib.rb \
    && apk add --no-cache \
            ruby \
            ruby-rdoc \
            ruby-irb \
    && gem install redis

COPY docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]
