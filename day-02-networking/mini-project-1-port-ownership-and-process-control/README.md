# Mini Project 1 – Port Ownership & Process Control

## Goal
Understand how Linux manages port ownership and why process management matters.

## Key Learnings
- Only one process can bind to a port at a time
- The kernel enforces port ownership
- kill -9 forcefully terminates a process without cleanup
- Graceful shutdowns are safer and predictable

## Tools Used
- ss
- ps
- kill
- python3 http.server

## Setup

- OS: Ubuntu Linux
- User: sudo user
- Tool: python3 http.server
- Port used: 8080

## Failure Scenarios

### Failure: Port Already in Use
- One service was already bound to port 8080
- Starting a second service on the same port failed
- Kernel returned "Address already in use"

## Debugging Steps

1. Identified port conflict error during service start
2. Used ss -tulnp to identify the process owning the port
3. Verified process details using ps
4. Terminated the process forcefully using kill -9
5. Restarted the service and stopped it gracefully

