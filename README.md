# AMD Ryzen Precision Boost Overdrive (PBO) Guide

A practical guide to configuring, testing, and troubleshooting **AMD Precision Boost Overdrive (PBO)** on supported Ryzen PCs.

> [!WARNING]
> PBO, Curve Optimizer, boost overrides, and related controls can operate a processor outside its stock configuration. Settings that work on one CPU may be unstable on another. Make changes incrementally, monitor temperatures, and validate stability.

## What is PBO?

AMD Ryzen processors use Precision Boost to dynamically manage clock speed according to workload, temperature, power, current, firmware limits, and other operating conditions.

**Precision Boost Overdrive (PBO)** expands the limits available to that automatic boosting behavior on supported processors and motherboards. It is not the same as setting a traditional fixed all-core overclock.

## What this guide covers

- PBO compatibility and prerequisites
- BIOS preparation and recovery
- PPT, TDC, and EDC
- PBO modes and limits
- Curve Optimizer
- Boost Clock Override and Scalar
- Baseline benchmarking
- Stability and temperature testing
- WHEA errors, crashes, and troubleshooting
- ASUS, MSI, Gigabyte, and ASRock BIOS navigation

## Recommended workflow

1. Confirm that your CPU, motherboard, and BIOS expose the required PBO features.
2. Update BIOS and AMD chipset drivers when appropriate.
3. Record stock performance and temperatures.
4. Enable PBO without changing several advanced settings at once.
5. Benchmark again.
6. Tune Curve Optimizer gradually.
7. Stability-test heavy and light/single-core workloads.
8. Validate with the games and applications you actually use.
9. Save a known-good BIOS profile.

## Terminology

### PPT — Package Power Tracking
A processor/socket power limit used by PBO. Raising it provides additional headroom; it does not guarantee higher performance.

### TDC — Thermal Design Current
A sustained-current limit relevant to longer, thermally constrained workloads.

### EDC — Electrical Design Current
A peak/short-duration current limit that can affect boost behavior under high instantaneous demand.

### Curve Optimizer
Adjusts the processor's voltage/frequency curve. Negative values can reduce the voltage requested for a given operating point and may improve efficiency or boost headroom, but overly aggressive values can cause instability.

A larger negative number is **not automatically better**.

## Golden rule

**Do not copy another person's PBO or Curve Optimizer values and assume they are stable.**

Even two processors with the same model number can behave differently.

## Documentation

### Start here
- [Compatibility](docs/compatibility.md)
- [BIOS Setup](docs/bios-setup.md)
- [PBO Basics](docs/pbo-basics.md)
- [PPT, TDC & EDC](docs/power-limits.md)

### Tuning and validation
- [Curve Optimizer](docs/curve-optimizer.md)
- [Stability Testing](docs/stability-testing.md)
- [Troubleshooting](docs/troubleshooting.md)
- [Frequently Asked Questions](docs/faq.md)

### Motherboard BIOS guides
- [ASUS](docs/motherboard-guides/asus.md)
- [MSI](docs/motherboard-guides/msi.md)
- [Gigabyte](docs/motherboard-guides/gigabyte.md)
- [ASRock](docs/motherboard-guides/asrock.md)

## Scope

This project aims to cover supported desktop Ryzen platforms generally rather than prescribe one configuration for every CPU. Exact feature availability varies by processor generation, motherboard, BIOS/AGESA version, and OEM restrictions.

## ☕ Support This Guide

If this guide helped you tune or better understand your Ryzen system, you can support the project here:

[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-Support%20DeshaunDoesTech-yellow?logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/DeshaunDoesTech)

**[Buy Me a Coffee →](https://buymeacoffee.com/DeshaunDoesTech)**

Support is completely optional and helps with maintaining and expanding the guide.

## Disclaimer

This is an independent community guide and is not affiliated with or endorsed by AMD or any motherboard manufacturer. CPU tuning can cause instability, lost work, reduced performance, or other problems if configured incorrectly. Understand the controls and keep a recovery path before changing firmware settings.
