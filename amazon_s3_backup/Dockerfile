ARG BUILD_FROM=ghcr.io/hassio-addons/base:16.3.2
# hadolint ignore=DL3006
FROM ${BUILD_FROM}
ENV LANG C.UTF-8

# add aws-cli and deps
RUN apk add --no-cache \
        python3 \
        py3-pip \
        groff \
        less \
        jq \
        aws-cli

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION="Amazon S3 Backup Add-on for Home Assistant"
ARG BUILD_NAME="Amazon S3 Backup"
ARG BUILD_REF=main
ARG BUILD_REPOSITORY="daveshow/amazon_s3_backup"
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="David Peters (https://github.com/daveshow)" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    org.opencontainers.image.vendor="Home Assistant Add-ons" \
    org.opencontainers.image.authors="David Peters (https://github.com/daveshow)" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://github.com/daveshow/ha-addons/tree/main/amazon_s3_backup" \
    org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}
