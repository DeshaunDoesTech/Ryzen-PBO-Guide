# Frequently Asked Questions (FAQ)

Answers to common questions about AMD Precision Boost Overdrive (PBO), Curve Optimizer, temperatures, stability, and this guide.

> [!IMPORTANT]
> PBO behavior and available settings vary by Ryzen processor, motherboard, BIOS/AGESA version, cooling, and system manufacturer. A setting that works well on one system is not guaranteed to work on another.

## What is Precision Boost Overdrive (PBO)?

PBO is an AMD Ryzen feature that works with the processor's automatic boost behavior. On supported systems, it can expand power/current and other operating limits available to the boost algorithm instead of setting one fixed CPU clock.

## Is PBO the same as manually overclocking my CPU?

No. A traditional manual overclock commonly sets a fixed multiplier/frequency and often a manually selected voltage. PBO instead works with Ryzen's dynamic boosting system, allowing the processor to continue adjusting clocks according to workload and operating conditions.

## Does my Ryzen CPU support PBO?

Support depends on the exact processor, motherboard, BIOS, and sometimes the system manufacturer. Some CPUs expose more PBO features than others, and OEM/prebuilt systems may restrict the controls.

Start with the [Compatibility Guide](compatibility.md).

## Where do I find PBO in my BIOS?

The exact path varies by motherboard. Common locations include **AMD Overclocking**, **Advanced CPU Configuration**, and manufacturer-specific overclocking menus.

See the [step-by-step BIOS guide](bios-setup.md).

## Is "Auto" the same as enabling PBO?

Not necessarily. The meaning of **Auto** is firmware-dependent and can represent the board's default behavior. If your BIOS offers an explicit **Enabled** option and your goal is simply to enable PBO, use the documented option for your board.

## What are PPT, TDC, and EDC?

- **PPT (Package Power Tracking)** relates to the processor/socket power limit used by the boost algorithm.
- **TDC (Thermal Design Current)** relates to sustained current.
- **EDC (Electrical Design Current)** relates to shorter-duration/peak current.

Increasing these values does not automatically increase performance.

Read [PPT, TDC & EDC](power-limits.md) for more information.

## Should I set PPT, TDC, and EDC to the maximum?

No. Higher limits can increase power consumption and heat without producing a useful performance improvement. Determine what is actually limiting your processor and compare every change against a stock baseline.

## What is Curve Optimizer?

Curve Optimizer modifies the voltage/frequency curve used by supported Ryzen processors. Negative Curve Optimizer values can reduce requested voltage at points on that curve and may improve efficiency or create additional boost headroom.

See the [Curve Optimizer Guide](curve-optimizer.md).

## Is a more negative Curve Optimizer value always better?

No. An aggressive negative curve can become unstable. Possible symptoms include application crashes, game crashes, reboots, BSODs, WHEA errors, idle instability, or failures that appear only under lightly threaded workloads.

## Can I copy somebody else's Curve Optimizer settings?

You can use another configuration as a reference, but you should not assume it will be stable on your CPU. Individual processors—and individual cores within a processor—can have different voltage/frequency characteristics.

## Should I use all-core or per-core Curve Optimizer?

All-core tuning is simpler and can be useful for learning how your CPU responds. Per-core tuning allows individual cores to use different values and can provide finer control, but it requires considerably more stability testing.

## Why does my PC pass a stress test but crash while gaming or sitting idle?

Curve Optimizer instability does not always appear during a heavy all-core workload. A particular core may become unstable during high single-core boost, a lightly threaded workload, or a low-load transition. Include single-core, light-load, idle, sleep/wake, and real-world testing.

## What is a WHEA error?

Windows Hardware Error Architecture (WHEA) reports hardware-related errors detected by the system. If new WHEA errors begin appearing after CPU tuning, treat them as a stability warning and investigate or revert the recent changes.

## Will enabling PBO always make my CPU faster?

No. Performance depends on the workload and on which constraint the processor encounters. Temperature, power, current, voltage/frequency behavior, firmware limits, and cooling can all affect the result.

Always benchmark before and after tuning.

## Why did my temperatures increase after enabling PBO?

Additional boost headroom can allow the processor to consume more power when conditions permit it, which can increase heat output. Compare performance as well as temperature: extra heat is not necessarily useful if the workload gains little or no performance.

## Is a lower CPU temperature always better for performance?

Lower temperature can provide additional boost headroom, but temperature is only one part of Ryzen's boost behavior. Power, current, voltage/frequency limits, workload, and firmware configuration can also constrain performance.

## What is PBO Scalar?

Scalar is an advanced PBO control that can influence how the boost algorithm treats reliability-related limits. It should not be treated as a simple "performance multiplier." Leave it at its default while learning PBO and change it only when you understand why you are doing so.

## What is Max CPU Boost Clock Override?

On supported processors, Boost Clock Override can adjust the maximum frequency ceiling available to automatic boosting. It does not force the CPU to run at the selected additional frequency. The processor still needs sufficient electrical, thermal, and workload headroom.

## Should I enable PBO and Curve Optimizer at the same time?

For troubleshooting purposes, enable and test basic PBO first. Establish its effect before introducing Curve Optimizer, manual power limits, Scalar, or Boost Clock Override. Changing one category at a time makes problems much easier to isolate.

## Can PBO damage my CPU?

CPU tuning changes operating behavior and can increase power, current, voltage exposure, and temperature depending on the configuration. Use supported controls responsibly, maintain adequate cooling, monitor the system, and understand that overclocking-related operation may have warranty implications.

## What should I do if the PC no longer boots?

Use the recovery procedure documented by your motherboard manufacturer. This commonly involves clearing CMOS or using a dedicated BIOS recovery feature. This is why you should learn the recovery procedure before beginning CPU tuning.

See [Troubleshooting](troubleshooting.md).

## How do I know whether my PBO tune is actually better?

Compare it against a repeatable stock baseline. Look at:

- Real application/game performance
- Benchmark results
- Effective clock speeds
- CPU temperature
- Package power
- PPT/TDC/EDC behavior
- Stability and WHEA errors
- Noise and cooling requirements

A tune that reports a higher clock but performs worse or becomes unstable is not an improvement.

## Do I need Ryzen Master?

No. PBO can be configured through supported motherboard firmware. Ryzen Master can be useful for monitoring and supported tuning workflows in Windows, but this repository focuses primarily on understanding and configuring PBO through BIOS/UEFI.

## Does this guide provide universal "best PBO settings"?

No—and intentionally so. There is no single configuration that is optimal and stable for every Ryzen processor, motherboard, cooler, BIOS, and workload.

The goal of this project is to teach you how to understand, test, and validate your own configuration rather than copy unexplained numbers.

## Is this an official AMD guide?

No. Ryzen-PBO-Guide is an independent community project and is not affiliated with or endorsed by AMD or any motherboard manufacturer.

---

Still having a problem? Start with the [Troubleshooting Guide](troubleshooting.md), or open an issue in the repository with your **CPU, motherboard, BIOS version, cooling setup, relevant PBO settings, and the exact problem you are experiencing**.
