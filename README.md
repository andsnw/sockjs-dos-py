# Meteor SockJS 0.3.19 Denial of Service POC
[SockJS v0.3.19](https://github.com/sockjs/sockjs-node/issues/252) calls `res.end` instead of `res.write` when receiving websocket upgrade requests. SockJS is used in a number of packages as a dependency.

Vulnerable versions affected:
* Meteor JS <1.10.2 which use SockJS 0.3.19


## Usage
Install Python, then run in cmd/terminal:
```
pip install requests
python poc.py --target <domain>
```

## Remediation
Update SockJS to 0.3.20
