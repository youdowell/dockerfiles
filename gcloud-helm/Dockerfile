FROM youdowell/gcloud
MAINTAINER Andrew Usov <andrew.usov@youdowell.com>

# Install Helm
ENV HELM_VERSION="v2.6.2" \
	HELM_SHASUM="ba807d6017b612a0c63c093a954c7d63918d3e324bdba335d67b7948439dbca8"
	
ENV HELM_URL="https://storage.googleapis.com/kubernetes-helm/helm-${HELM_VERSION}-linux-amd64.tar.gz" \
	HELM_FILENAME="helm-${HELM_VERSION}-linux-amd64.tar.gz"

ADD ${HELM_URL} /tmp/${HELM_FILENAME}

RUN \
	(echo "${HELM_SHASUM}  /tmp/${HELM_FILENAME}" | sha256sum -c -) && \
	tar -zxvf "/tmp/${HELM_FILENAME}" -C /tmp && \
	mv /tmp/linux-amd64/helm /usr/local/bin/helm && \
	helm init --client-only && \
  	rm -rf /tmp
