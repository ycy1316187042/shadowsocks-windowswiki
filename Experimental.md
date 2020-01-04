# Experimental Features

Features list here are not fully tested and may be removed in future releases.

#### Custom GFWList source URL (v4.1.9.0)
In `gui-config.json` file, add `gfwListUrl` key-value. Shadowsocks would fetch the GFWList content from this URL.

#### Listening on local IPv6 interface (v4.1.7)

In `gui-config.json` file, add `isIpv6Enabled` key-value. Default value is `false`.
```
  ...
  "isDefault": false,
  "isIPv6Enabled": true,
  "localPort": 8388,
  ...
```