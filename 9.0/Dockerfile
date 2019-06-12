FROM camptocamp/odoo-project:9.0-3.1.2
MAINTAINER Camptocamp

RUN set -x; \
    apt-get update \
    && apt-get install -y wget --no-install-recommends \
    && apt-get install -y perl --no-install-recommends \
    && apt-get install -y make --no-install-recommends \
    && apt-get install -y pkg-config gobject-introspection libglib2.0-dev  libxslt1-dev \
    && apt-get install -y --no-install-recommends build-essential \
    && apt-get install -y --no-install-recommends libxml2-dev libltdl-dev \
    && apt-get install -y --no-install-recommends zlib1g zlib1g-dev \
    && wget https://www.openssl.org/source/openssl-1.1.0k.tar.gz \
    && tar xvzf openssl-1.1.0k.tar.gz \
    && cd openssl-1.1.0k \
    && ./config \
    && make \
    && make install \
    && cd .. \
    && wget http://www.aleksey.com/xmlsec/download/xmlsec1-1.2.28.tar.gz \
    && tar xvzf xmlsec1-1.2.28.tar.gz \
    && cd xmlsec1-1.2.28 \
    && ./configure \
    && make \
    && make install \
    && cd ..

 RUN set -x; \
        apt-get install -y --no-install-recommends python-dev \
        && pip install six \
        && wget https://dev.entrouvert.org/releases/lasso/lasso-2.6.0.tar.gz \
        && tar xvzf lasso-2.6.0.tar.gz \
        && cd lasso-2.6.0 \
        && ./configure --disable-perl --disable-php --disable-java --disable-coldfusion \
        && make \
        && make install \
