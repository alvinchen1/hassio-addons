ARG BUILD_FROM=ghcr.io/home-assistant/{arch}-base:latest
FROM ${BUILD_FROM}

# Set Fluent Bit version explicitly
ARG FLUENTBIT_VERSION=3.0.4
ARG BUILD_ARCH

# Labels required by Home Assistant Supervisor
LABEL \
    io.hass.name="Fluent Bit" \
    io.hass.description="High-performance log processor and forwarder" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version="${FLUENTBIT_VERSION}"

# Install Fluent Bit
RUN \
    apk add --no-cache \
        curl \
        ca-certificates \
        bash \
        python3 \
        py3-pip \
        jq \
    && \
    case "${BUILD_ARCH}" in \
        amd64)   FB_ARCH="x86_64" ;; \
        aarch64) FB_ARCH="arm64" ;; \
        armv7)   FB_ARCH="armhf" ;; \
        *) echo "Unsupported architecture: ${BUILD_ARCH}" && exit 1 ;; \
    esac \
    && \
    curl -L "https://github.com/fluent/fluent-bit/releases/download/v${FLUENTBIT_VERSION}/fluent-bit-${FLUENTBIT_VERSION}-${FB_ARCH}.tar.gz" \
        -o /tmp/fluentbit.tar.gz \
    && \
    mkdir -p /opt/fluent-bit \
    && \
    tar -xzf /tmp/fluentbit.tar.gz -C /opt/fluent-bit --strip-components=1 \
    && \
    rm /tmp/fluentbit.tar.gz

# Copy add-on files
COPY run.py /run.py
COPY fluentbit.key /fluentbit.key

# Ensure Python entrypoint is executable
RUN chmod +x /run.py

# Expose Fluent Bit HTTP server + metrics
EXPOSE 2020/tcp
EXPOSE 2021/tcp

# Disable s6-overlay (we use a direct entrypoint)
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
ENTRYPOINT ["/usr/bin/python3", "/run.py"]