# Meteor SockJS 0.3.19 Denial of Service POC
[SockJS v0.3.19](https://github.com/sockjs/sockjs-node/issues/252) calls `res.end` instead of `res.write` when receiving websocket upgrade requests. This causes an `Error [ERR_STREAM_WRITE_AFTER_END]: write after end` which crashes the app utilising the vulnerable SockJS.

Vulnerable versions affected:
* Meteor JS <1.10.2 which use SockJS 0.3.19
* SockJS 0.3.19

## Usage
This POC is targeted towards vulnerable MeteorJS apps. To customise, change the payloads from `/sockjs` to corresponding routes of managed by SockJS.

Install Python, then run in cmd/terminal:
```
pip install requests
python poc.py --target <domain>
```

## Remediation
Update SockJS to 0.3.20
