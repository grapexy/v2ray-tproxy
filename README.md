Fork of [v2ray-core](https://github.com/v2fly/v2ray-core) with optional support for keeping
source address for outgoing connections. This is useful for proxying traffic with `tproxy`
without relying on NAT.

Usage:

Simply configure the `outbound` connection type with `"sendThrough": "0.0.0.0"` and source IP
will be automatically set to the IP of incoming connection:

```json
"outbounds": [
    {
        "protocol": "freedom",
        "sendThrough": "0.0.0.0",
        "streamSettings": {
            "sockopt": {
                "tproxy": "tproxy"
            }
        },
        "tag": "freedom"
    }
]
```

This was only tested with TCP traffic and UDP may or may not work.
