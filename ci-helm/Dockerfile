FROM youdowell/gcloud-helm
MAINTAINER Andrew Usov <andrew.usov@youdowell.com>

# Install make, git, envsubst
RUN \
    apk add --no-cache --virtual build_deps gettext && \
    apk add --no-cache git make libintl && \
    cp /usr/bin/envsubst /usr/local/bin/envsubst && \
    apk del build_deps
