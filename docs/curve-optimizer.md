# Curve Optimizer

Curve Optimizer changes the voltage/frequency curve used by supported Ryzen processors.

## Negative Curve Optimizer

A negative value can reduce the voltage requested at points on the curve. A successful tune can improve efficiency and may create additional thermal/electrical headroom.

It does not guarantee lower temperatures or higher performance in every workload.

## All-core vs. per-core

All-core applies the same magnitude across cores and is simpler to test. Per-core tuning allows different values for different cores but requires substantially more validation.

## Conservative process

1. Establish a stock baseline.
2. Enable the desired PBO mode.
3. Start with a small negative magnitude.
4. Test multi-core workloads.
5. Test single-core/lightly threaded workloads.
6. Test idle-to-load transitions and normal desktop use.
7. Increase magnitude gradually only while stable.
8. Reduce magnitude when instability appears.

Watch for WHEA errors, reboots, BSODs, crashes, benchmark errors, reduced effective clocks, and performance regression.

Next: [Stability Testing](stability-testing.md)
