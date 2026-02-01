# Linux App Server – Day 1 Main Project

## What I built
A simple Python HTTP server running on port 8080 to understand Linux process and port behavior.

## How it works
The server starts a Python process that binds to TCP port 8080 and serves HTTP responses.

## Observations
- The server runs as a foreground process by default.
- Pressing CTRL+C sends a SIGINT and terminates the process cleanly.
- When the process exits, the port is released automatically.

## Failures / Experiments
- Running the server in the background keeps the port occupied.
- Starting another process on the same port causes a port conflict error.

## What I learned
- Ports are owned by processes, not applications.
- Clean shutdown releases system resources.
- Port conflicts occur only when a process is still running.


- Running the server in background keeps the port occupied.
- Sending SIGTERM using `kill` stops the process cleanly.
- After termination, the port is released and reusable.
- Force killing (SIGKILL) immediately stops the process without cleanup.
