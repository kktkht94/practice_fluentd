FROM fluent/fluentd:v1.7-debian-1

USER root

RUN buildDeps="sudo make gcc g++ libc-dev" \
 && apt-get update \
 && apt-get install -y --no-install-recommends $buildDeps \
        build-essential \
        libssl-dev libxml2-dev libxslt1-dev \
 && sudo gem install fluentd-ui \
 && fluentd-ui setup \
 && sudo gem sources --clear-all \
 && SUDO_FORCE_REMOVE=yes \
    apt-get purge -y --auto-remove \
                  -o APT::AutoRemove::RecommendsImportant=false \
                  $buildDeps \
 && rm -rf /var/lib/apt/lists/* \
 && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

CMD ["fluentd-ui", "start"]