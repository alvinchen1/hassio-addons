FROM ghcr.io/hassio-addons/debian-base:9.4.0

RUN apt-get update -y && \
    apt-get install --no-install-recommends -y gpg && \
    rm -rf /var/lib/apt/lists/*

COPY fluentbit.key /fluentbit.key

RUN cat /fluentbit.key | gpg --dearmor > /usr/share/keyrings/fluentbit-keyring.gpg && \
    rm /fluentbit.key

RUN . /etc/os-release && \
    export CODENAME=$(echo "${VERSION_CODENAME}" | tr '[:upper:]' '[:lower:]') && \
    echo "deb [signed-by=/usr/share/keyrings/fluentbit-keyring.gpg] https://packages.fluentbit.io/debian/${CODENAME} ${CODENAME} main" \
    > /etc/apt/sources.list.d/fluentbit.list

RUN apt-get update -y && \
    apt-get install --no-install-recommends -y \
        python3 \
        python3-pip \
        fluent-bit && \
    rm -rf /var/lib/apt/lists/*

COPY run.py /run.py

CMD ["python3", "-u", "/run.py"]