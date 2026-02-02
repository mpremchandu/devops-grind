# Mini Project 2 – DNS & Connectivity Debugging

## Goal
Understand the difference between network connectivity and DNS resolution,
and learn why DNS issues are difficult to debug in real systems.

## Key Learnings
- IP connectivity and DNS resolution are separate layers
- DNS results can be cached and reused
- /etc/resolv.conf does not always control DNS behavior
- systemd-resolved manages DNS on modern Ubuntu systems
- DNS queries may be intercepted or answered by the network
- Local testing does not always reflect real DNS behavior

## Tools Used
- ping
- nslookup
- dig

## Setup

- OS: Ubuntu Linux
- User: sudo-enabled non-root user
- Network: Home / local network
- DNS Resolver: systemd-resolved
- Tools used:
  - ping
  - nslookup
  - dig (optional)

## Failure Scenarios

### Scenario 1: Internet Connectivity Check
- Ping to IP address (8.8.8.8) was successful
- Confirmed network and routing were working

### Scenario 2: DNS Change via resolv.conf
- Modified nameserver entry in /etc/resolv.conf
- DNS resolution continued to work
- Learned that resolv.conf is managed by systemd-resolved

### Scenario 3: Invalid DNS Server
- Set nameserver to an unreachable IP (10.255.255.1)
- DNS queries still succeeded due to:
  - DNS caching
  - Network-level DNS interception

## Debugging Steps

1. Verified basic connectivity using ping to an IP address
2. Tested DNS resolution using domain names
3. Used nslookup to identify which DNS server was being queried
4. Forced DNS queries to a specific server using nslookup <domain> <server>
5. Identified systemd-resolved as the active DNS resolver
6. Understood the impact of DNS caching and network interception

