# BIOS Setup

Before tuning PBO, establish a configuration you can recover from.

## Preparation

1. Photograph or record important BIOS settings.
2. Learn the motherboard's Clear CMOS/recovery procedure.
3. Record stock performance, temperatures, package power, and effective clocks.
4. Keep memory tuning unchanged while establishing the CPU baseline.

# Step-by-step: Enable Precision Boost Overdrive in BIOS

> [!NOTE]
> BIOS names and menu paths vary by motherboard manufacturer, model, and BIOS/AGESA version. If a PBO option is missing, confirm that your exact CPU and motherboard firmware support it.

## 1. Enter the UEFI/BIOS

1. Restart the PC.
2. During startup, repeatedly press the motherboard's BIOS key. **Delete** and **F2** are the most common.
3. If the firmware opens in an Easy/EZ Mode, switch to **Advanced Mode** when necessary.

## 2. Locate AMD overclocking controls

Look for a menu named **AMD Overclocking**, **Precision Boost Overdrive**, **Advanced CPU Configuration**, or a manufacturer-specific CPU/overclocking menu.

A common generic path is:

```text
Advanced Mode
  → AMD Overclocking
    → Accept (if an AMD overclocking warning appears)
      → Precision Boost Overdrive
```

Your board may use a different path.

## 3. Open Precision Boost Overdrive

Select **Precision Boost Overdrive**.

Depending on the firmware, possible choices may include:

- Auto
- Disabled
- Enabled
- Advanced
- Manual
- Motherboard or motherboard-defined limits

The exact choices vary by platform.

## 4. Enable PBO

For a first PBO test, choose **Enabled** if the BIOS provides that option.

If the BIOS requires **Advanced** to expose PBO controls, select **Advanced**, but leave additional settings at their defaults initially. Do not immediately change PPT, TDC, EDC, Scalar, Boost Clock Override, Curve Optimizer, and thermal limits all at once.

> [!IMPORTANT]
> **Auto is not necessarily the same as explicitly enabling PBO.** Firmware behavior varies. Use the explicit **Enabled** setting when the goal is simply to turn PBO on and that option is available.

## 5. Save and restart

1. Press **F10** on most motherboards to open **Save & Exit**.
2. Review the list of changed settings.
3. Confirm the changes.
4. Allow the PC to restart normally.

## 6. Verify the system

Once back in the operating system:

1. Confirm the PC boots normally.
2. Monitor CPU temperature.
3. Run the same benchmark you recorded at stock.
4. Compare performance, temperature, package power, and effective clocks with your baseline.
5. Check for crashes, reboots, WHEA errors, or other abnormal behavior.

Enabling PBO does not guarantee a measurable performance increase. The result depends on the CPU, cooling, motherboard limits, firmware, workload, and other constraints.

# Common manufacturer paths

These are starting points, not universal paths. BIOS layouts can change between boards and firmware releases.

## ASUS

A common ASUS AM5 path is similar to:

```text
Advanced Mode
  → Advanced
    → AMD Overclocking
      → Precision Boost Overdrive
```

Some ASUS boards also expose PBO-related controls under **AI Tweaker** or **Extreme Tweaker**.

See the [ASUS guide](motherboard-guides/asus.md).

## MSI

Depending on the MSI BIOS generation, PBO may be accessible through EZ Config or a path similar to:

```text
Advanced Mode
  → OC / Overclocking
    → Advanced CPU Configuration
      → Precision Boost Overdrive
```

See the [MSI guide](motherboard-guides/msi.md).

## Gigabyte / AORUS

A common location on supported Gigabyte boards is:

```text
Advanced Mode
  → Tweaker
    → Advanced CPU Settings
      → Precision Boost Overdrive
```

Some firmware versions instead expose the standard **AMD Overclocking** menu.

See the [Gigabyte guide](motherboard-guides/gigabyte.md).

## ASRock

Look for **AMD Overclocking** or CPU configuration controls in Advanced Mode, then locate **Precision Boost Overdrive**. Exact paths differ substantially across ASRock generations.

See the [ASRock guide](motherboard-guides/asrock.md).

# If PBO is missing

Do not assume the setting is merely hidden. Check:

1. Whether the exact CPU supports PBO.
2. Whether the motherboard/system supports CPU overclocking features.
3. Whether a BIOS update changes feature availability.
4. Whether the PC is an OEM/prebuilt system whose manufacturer restricts overclocking controls.
5. Whether PBO is located under a second AMD Overclocking/CPU configuration menu.

# After enabling PBO

Run the system with basic PBO enabled before making additional changes. Establish whether PBO alone changes performance, temperature, or power behavior.

Then continue to:

1. [PBO Basics](pbo-basics.md)
2. [PPT, TDC & EDC](power-limits.md)
3. [Curve Optimizer](curve-optimizer.md)
4. [Stability Testing](stability-testing.md)

## Change one category at a time

Do not simultaneously change PBO limits, Curve Optimizer, memory timings, Scalar, and boost override. Incremental changes make instability easier to diagnose.

## References

- [AMD Ryzen Master](https://www.amd.com/en/products/software/ryzen-master.html)
- [AMD Ryzen Master User Guide](https://docs.amd.com/r/en-US/68886-ryzen-master-user-guide/CPU)
- [ASUS AMD AM5 BIOS Manual](https://dlcdnets.asus.com/pub/ASUS/mb/13MANUAL/PRIME_PROART_TUF_GAMING_AMD_AM5_Series_BIOS_EM_WEB_EN.pdf)
- [MSI Click BIOS](https://www.msi.com/Landing/msi-click-bios-intel-amd-motherboard)
