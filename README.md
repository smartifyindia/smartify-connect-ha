# Smartify Connect for Home Assistant

Control your Home Assistant devices from the **Smartify Home** app. Smartify Connect runs next to Home Assistant and opens an outbound connection to Smartify, so it works behind any home router with no port forwarding.

## Home Assistant OS (Green, Yellow, Raspberry Pi)

[![Add repository to my Home Assistant](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fsmartifyindia%2Fsmartify-connect-ha)

Or in Home Assistant: **Settings → Apps → App store → ⋮ → Repositories**, add `https://github.com/smartifyindia/smartify-connect-ha`. Then install **Smartify Connect**, start it, and open **Smartify** in the sidebar for your pairing code and QR.

## Home Assistant in Docker

1. In Home Assistant, create a long-lived access token: your profile → **Security** → **Long-lived access tokens**.
2. Run Smartify Connect next to it:

```bash
docker run -d --name smartify-connect --restart unless-stopped \
  -v smartify-connect:/data \
  -e HA_URL=http://<home-assistant-address>:8123 \
  -e HA_TOKEN=<token> \
  ghcr.io/smartifyindia/smartify-connect:latest
```

3. Get your pairing code and QR with `docker logs smartify-connect`.

## Then, in the Smartify Home app

**Add device → Connect Home Assistant**, scan the QR or type the code, and choose which devices to add.

See [smartify_connect/DOCS.md](smartify_connect/DOCS.md) for what Smartify can and can't see.
