# Day 2 – Networking & System Internals (Recap)

## Overview
Day 2 focused on understanding how a Linux system handles networking at different layers
and why applications can fail to be reachable even when they are running.

The emphasis was on **debugging mindset**, not just commands.

---

## Key Learnings

### 1. Running Does Not Mean Reachable
A service can be running and still be inaccessible due to:
- No process listening on the port
- Incorrect interface binding (127.0.0.1 vs 0.0.0.0)
- Firewall rules blocking access

---

### 2. The Kernel Controls Networking
All networking actions are mediated by the Linux kernel:
- Ports are owned by the kernel
- Processes request ports from the kernel
- The kernel decides how traffic is routed
- Firewalls are enforced by the kernel

Applications do not control networking directly.

---

### 3. Why `ss -tulnp` Is Critical
Application logs may say “server started”, but only the kernel knows:
- Which ports are open
- Which process owns a port
- Which interface a service is bound to

`ss -tulnp` shows the actual state of the system.

---

### 4. Firewall Testing Can Be Misleading
Testing access from the same machine is unreliable because:
- Loopback traffic is always allowed
- Local traffic may bypass firewall ingress rules

Real firewall validation must be done from another machine.

---

### 5. DNS Is More Complex Than It Looks
- DNS resolution is separate from network connectivity
- DNS results are cached
- Modern Ubuntu uses systemd-resolved
- Editing /etc/resolv.conf does not always change DNS behavior
- DNS queries may be intercepted by the network

This explains why DNS issues are often inconsistent and hard to debug.

---

## Projects Completed

- **Main Project**: Network debugging (ports, binding, firewall)
- **Mini Project 1**: Port ownership and process control
- **Mini Project 2**: DNS vs connectivity debugging

---

## One Line to Remember

> If it works on the server, it can still be down for users.

---

## Tools Used

- curl
- ss
- ufw
- ping
- nslookup
- python3 http.server
