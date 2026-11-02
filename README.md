# AdrenoFirmware

Adreno firmware and HFI protocol support.

GMU cold start and HFI work on sheng hardware.

Build and interface details: [documentation](https://unixnu.com/drivers/adreno-firmware). Component sources and dependencies: [catalog](https://unixnu.com/reference/components).

`AdrenoHfiStartupConfig.performance_table` explicitly selects the A6xx/A7xx layout or the variable A8xx TABLE message. A8xx callers provide dependency votes for each GPU level. The serialization and failure paths pass software-peer checks; this does not provide board voltage data or establish A830 firmware execution.

`AdrenoHfiGen8Votes` derives MX/BX dependency votes from the selected primary corner and validated command-db rail tables. The legacy A7xx vote interface retains its existing behavior. SM8750 command-db parsing and speed-bin policy live in the SoC and device repositories.
