# Tailscale Installation

1. Install Tailscale
```bash
curl -fsSL https://tailscale.com/install.sh | sh
```
2. Start and authenticate
 ```bash
sudo tailscale up
```
3. Verify connection
```bash
tailscale status
```
Output example
```bash
100.x.x.x   debian-server   active
100.x.x.x   laptop          active
100.x.x.x   desktop         active
```
4. Download Tailscale on other devices and connect
