ARG BUILD_FROM=ghcr.io/home-assistant/{arch}-debian-base:latest
FROM ${BUILD_FROM}

# Set Fluent Bit version explicitly
ARG FLUENTBIT_VERSION=3.2.10

# Labels required by Home Assistant Supervisor
LABEL \
    io.hass.name="Fluent Bit" \
    io.hass.description="High-performance log processor and forwarder" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version="${FLUENTBIT_VERSION}"

# Install prerequisites
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends curl gpg python3 python3-pip

# Add Fluent Bit signing key
COPY fluentbit.key /fluentbit.key
RUN cat /fluentbit.key | gpg --dearmor > /usr/share/keyrings/fluentbit-keyring.gpg && \
    rm /fluentbit.key

# Add Fluent Bit APT repository
RUN . /etc/os-release && \
    CODENAME=$(echo "${VERSION_CODENAME}" | tr '[:upper:]' '[:lower:]') && \
    echo "deb [signed-by=/usr/share/keyrings/fluentbit-keyring.gpg] https://packages.fluentbit.io/debian/${CODENAME} ${CODENAME} main" \
        > /etc/apt/sources.list.d/fluentbit.list

# Install Fluent Bit
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends fluent-bit=${FLUENTBIT_VERSION}

# Copy add-on files
COPY run.py /run.py
RUN chmod +x /run.py

# Expose Fluent Bit HTTP server + metrics
EXPOSE 2020/tcp
EXPOSE 2021/tcp

ENTRYPOINT ["/usr/bin/python3", "/run.py"]