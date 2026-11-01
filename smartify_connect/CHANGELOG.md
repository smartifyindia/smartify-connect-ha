# Changelog

## 0.3.2
- Security hardening: Smartify can only run the services the app actually uses, on the device's own domain, and a call can no longer reach devices you didn't add.
- Messages from Smartify are ignored until the hub is paired; removing the hub in the app now drops its device list and session straight away.
- Matter setup codes are checked before they reach Home Assistant.
- The Docker status page (STATUS_PORT) refuses unknown host names, which blocks DNS-rebinding pages from reading the pairing code. Set STATUS_HOSTS if you open it by a host name.
- Device serial numbers are no longer sent to Smartify.
- Includes the connector updates since 0.3.1: every non-private device type, sanitised states, per-entity size limits, and acknowledged delivery to Smartify.

## 0.3.1
- Fix startup crash (`Dynamic require of "fs" is not supported`) in Docker and Home Assistant App builds caused by bundled CommonJS QR code dependencies.

## 0.3.0
- First public release: pairing by code or QR, a status page in the sidebar, lights, switches, fans, door and motion sensors, and Matter devices shared from Apple Home, Google Home or Alexa.
