ARG BUILD_FROM=node:22-alpine
FROM ${BUILD_FROM}
WORKDIR /app
COPY connect.mjs /app/connect.mjs
LABEL org.opencontainers.image.source="https://github.com/smartifyindia/smartify-connect-ha" \
      org.opencontainers.image.description="Smartify Connect: control Home Assistant devices from the Smartify Home app"
CMD ["node", "/app/connect.mjs"]
