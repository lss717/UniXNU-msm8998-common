# UniXNU-msm8998-common

Shared format 2 support for Qualcomm MSM8998 devices.

The initial skeleton preserves the OnePlus 5 measured and vendor-tree values
without claiming runtime support:

| Item | Value | Source |
| --- | --- | --- |
| CPU topology | 4x Kryo 280 Gold, 4x Kryo 280 Silver | Linux `msm8998.dtsi` |
| MPIDR values | `0..3`, `0x100..0x103` | Linux `msm8998.dtsi` |
| Timebase | 19.2 MHz | Linux `msm8998.dtsi`, phone measurements |
| GIC distributor | `0x17a00000`, `0x10000` | Linux `msm8998.dtsi` |
| GIC redistributor | `0x17b00000`, `0x100000`, stride `0x20000` | Linux `msm8998.dtsi` |
| UFS host controller | `0x1da4000`, `0x2500`, SPI 265 | Linux `msm8998.dtsi` |
| UFS PHY | `0x1da7000`, `0x1000` | Linux `msm8998.dtsi` |
| DWC3 controller | `0xa800000`, `0xcd00` | Linux `msm8998.dtsi` |

Micro-architecture strings are intentionally conservative: XNU currently uses
`arm,cortex-a53` and `arm,cortex-a73` for the two clusters. The vendor
`qcom,kryo280` identity remains recorded rather than being dropped.

The repository is a migration skeleton. It does not establish that the UFS,
USB, timer or platform operations are complete on XNU.
