ARG BUILD_FROM
FROM ${BUILD_FROM}

ARG PORTAINER_VERSION=2.19.4
ARG BUILD_ARCH

RUN case "${BUILD_ARCH}" in \
        amd64)   PORTAINER_ARCH="linux-amd64" ;; \
        aarch64) PORTAINER_ARCH="linux-arm64" ;; \
        armv7)   PORTAINER_ARCH="linux-armhf" ;; \
        armhf)   PORTAINER_ARCH="linux-armhf" ;; \
        *) echo "Unsupported architecture: ${BUILD_ARCH}" && exit 1 ;; \
    esac \
    && apk add --no-cache curl \
    && curl -L "https://github.com/portainer/portainer/releases/download/${PORTAINER_VERSION}/portainer-${PORTAINER_VERSION}-${PORTAINER_ARCH}.tar.gz" \
       | tar -xz -C /opt \
    && mv /opt/portainer /opt/portainer-bin \
    && apk del curl

EXPOSE 9000
EXPOSE 8000

CMD ["/opt/portainer-bin/portainer"]