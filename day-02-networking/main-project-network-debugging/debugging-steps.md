# Debugging Steps

1. Verified service was running using curl localhost
2. Checked port ownership using ss -tulnp
3. Identified interface binding (127.0.0.1 vs 0.0.0.0)
4. Tested access via server IP
5. Verified firewall status using ufw
6. Learned that firewall rules cannot be validated from the same host
