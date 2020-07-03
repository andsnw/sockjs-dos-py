# Meteor SockJS 0.3.19 Denial of Service POC
[SockJS v0.3.19](https://github.com/sockjs/sockjs-node/issues/252) calls `res.end` instead of `res.write` when receiving websocket upgrade requests.


## Usage
Install Python, then run in cmd/terminal:
```
pip install requests
python poc.py --target <domain>
```

## Remediation
Update SockJS to 0.3.20