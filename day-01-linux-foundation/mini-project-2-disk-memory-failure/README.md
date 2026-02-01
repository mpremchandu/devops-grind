# Disk and Memory Failure Lab

## Disk Full Experiment
- Simulated disk pressure by creating large files.
- Observed that applications may continue running but fail to write logs.
- Disk exhaustion often causes silent failures instead of crashes.

## Memory Pressure Experiment
- Applied controlled memory stress using stress tool.
- Observed significant CPU usage during memory pressure.
- With no swap configured, the OOM killer may terminate processes aggressively.

## Key Learnings
- Disk and memory issues often manifest indirectly.
- Memory pressure can cause high CPU usage due to kernel memory management.
- Monitoring resource usage is critical for system reliability.
