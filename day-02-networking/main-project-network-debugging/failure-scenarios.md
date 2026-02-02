# Failure Scenarios

## Failure 1: Service Stopped
- Python process stopped using Ctrl+C
- Port 8080 no longer listening
- curl localhost:8080 failed

## Failure 2: Service Bound to Loopback
- Service bound to 127.0.0.1
- curl localhost worked
- curl <server-ip> failed

## Failure 3: Firewall Enabled
- ufw enabled
- Local access continued to work
- Learned that local testing does not validate firewall ingress
