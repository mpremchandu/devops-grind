# Network Debugging – Main Project

## Goal
Understand how Linux handles networking at the process, port, binding, and firewall level.

## Key Learnings
- Ports are owned by the kernel, not applications
- A running service may still be unreachable
- Binding to 127.0.0.1 restricts external access
- Firewall ingress rules cannot be tested from the same host

## Tools Used
- curl
- ss
- ufw
- python3 http.server
