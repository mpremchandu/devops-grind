# Process Chaos Lab

## What was tested
Linux process behavior under CPU and priority stress.

## Experiments
- Ran CPU stress using stress tool.
- Observed process behavior using htop.
- Changed process priority using nice and renice.

## Observations
- CPU-intensive processes can starve others.
- Linux scheduler fairly distributes CPU but priority still matters.
- High CPU usage does not necessarily indicate application failure.

## Key Learnings
- Processes compete for CPU time.
- Nice values affect scheduling, not execution correctness.
- CPU saturation impacts system responsiveness.
