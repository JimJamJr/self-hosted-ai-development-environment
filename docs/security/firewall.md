# Firewall (UFW) 

The idea of a firewall install on the server was to reduce the attack surface for the network. I implemented and enabled it so that the server rejects any service that are not whitelisted on the server. This means that only the required ports for services such as remote access, Ollama, and Open WebUI are exposed.

Install was straight forward, I first installed UFW:
```bash
apt install ufw
```

Then I allowed ssh access:
```bash
ufw allow 22/tcp
```

Then I enabled the firewall:
```bash
ufw enable
```

Finally, I verified it was correctly configured:
```bash
# check status
ufw status

# expected response
22/tcp ALLOW
```

## How it works

The server has a rule set with a whitelist of allowed services. If a service requests access, it is checked against the rule set. Only services that are allowed pass through. Any other services are blocked. Therefore, security is quickly and easily enhanced.

## Benefits

- Reduced attack surface
- Protection against unwanted connections
- Layered security
