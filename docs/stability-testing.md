# Stability Testing

A PBO configuration is useful only if it remains stable in the workloads that matter to you.

## Test in stages

Start with a stock baseline. After each small change, run a short repeatable test. Include single-core and lightly threaded testing because Curve Optimizer instability can be core-specific. Then run sustained CPU workloads and your real games/applications.

## Monitor

- CPU temperature
- CPU package power
- PPT/TDC/EDC utilization
- Reported vs. effective clocks
- Benchmark score
- WHEA errors
- Application errors
- Reboots or BSODs

A system that boots without crashing can still be poorly tuned. Compare performance to the stock baseline.

Next: [Troubleshooting](troubleshooting.md)
