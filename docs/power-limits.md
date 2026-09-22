# PPT, TDC, and EDC

## PPT

**Package Power Tracking (PPT)** represents a processor/socket power limit used by the boost algorithm. Raising PPT gives additional permission to consume power when other conditions permit it; it does not force higher power consumption.

## TDC

**Thermal Design Current (TDC)** is associated with sustained current under thermally constrained operation.

## EDC

**Electrical Design Current (EDC)** is associated with shorter-duration/peak current.

## Tuning approach

1. Benchmark stock.
2. Observe which limits are approached.
3. Change only the relevant limit.
4. Repeat the same workload.
5. Compare performance, power, effective clocks, and temperature.

There is deliberately no universal PPT/TDC/EDC table here. Appropriate limits depend on CPU, platform, cooling, firmware, and goals.

Next: [Curve Optimizer](curve-optimizer.md)
