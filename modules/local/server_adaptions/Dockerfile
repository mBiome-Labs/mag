FROM community.wave.seqera.io/library/genomad:1.11.2--1e14efa5dfbf0dc3

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget

WORKDIR /build
RUN rm /opt/conda/bin/mmseqs
RUN wget --no-check-certificate https://mmseqs.com/latest/mmseqs-linux-sse41.tar.gz \
    && tar -xzvf mmseqs-linux-sse41.tar.gz \
    && cp mmseqs/bin/mmseqs /opt/conda/bin/ \
    && rm -rf mmseqs-linux-sse41*

WORKDIR /tmp

ENTRYPOINT ["/usr/local/bin/_entrypoint.sh"]
