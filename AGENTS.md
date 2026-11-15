# MSM8998 shared SoC support

This repository owns hardware and platform details shared by MSM8998-based
UniXNU ports. It must not contain device-specific partitions, board identity,
panel wiring, OnePlus 5 RAM reservations, or diagnostic boot arguments.

## Ownership

- Keep CPU topology, GICv3, timer, UFS, USB and other SoC-level resources here.
- Keep board wiring, firmware selection, reserved memory and partition policy
  in the corresponding device repository.
- Keep reusable driver implementations in the UniXNU component catalog.
- Keep bring-up probes and one-off safety bypasses out of this repository.

## Validation

The common device tree must compile through its test wrapper:

```sh
dtc -I dts -O dtb -i dts -o /tmp/msm8998.dtb tests/msm8998.dts
```

The patch series may be empty. Every added patch needs an explicit owner,
prerequisite order, applicable XNU revision and runtime consumer.
