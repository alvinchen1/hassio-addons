ARG BUILD_FROM=ghcr.io/home-assistant/{arch}-base:3.19
FROM ${BUILD_FROM}

# Set Portainer version
ARG PORTAINER_VERSION=2.20.3

# Install dependencies and Portainer
RUN apk add --no-cache curl \
    && curl -L https://github.com/portainer/portainer/releases/download/${PORTAINER_VERSION}/portainer-${PORTAINER_VERSION}-linux-${BUILD_ARCH}.tar.gz \
    | tar -xz -C /opt \
    && mv /opt/portainer /opt/portainer-bin \
    && apk del curl

# Expose Portainer ports
EXPOSE 9000
EXPOSE 8000

# Run Portainer
CMD ["/opt/portainer-bin/portainer"]