FROM solr:9.10.1

USER root

RUN apt-get update && \
    apt-get install -y --no-install-recommends git zip && \
    rm -rf /var/lib/apt/lists/*

# OpenShift: allow arbitrary UID to write where needed
RUN chgrp -R 0 /var/solr  && \
    chmod -R g+rwX /var/solr

# Switch to non-root (OpenShift will override with random UID anyway)
USER 8983

EXPOSE 8983

