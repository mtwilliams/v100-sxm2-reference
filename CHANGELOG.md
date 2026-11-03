# Reference changes

Versions identify the reference files someone used; they do not indicate hardware qualification. Future pinout corrections should name the connector/pad, previous assignment, new assignment and supporting evidence.

## Unreleased

Evidence-only update. No `Master_Signal`, pad coordinate or NVLink connection changed; only the `Confidence`, `Evidence_Status`, `Notes` and `Sources` columns of `data/connector-a.csv`, `data/connector-b.csv` and `data/pinout.csv` were edited.

- Added two sources: the Facebook/QCT Big Basin GPU baseboard (Open Compute Project; DGX-1-derived SXM2 reference schematic) and the OpenPOWER Advanced Accelerator Adapter specification v1.0.
- Connector A sideband contacts A18 PWR_GOOD, C18 I2C_ADDR0, H18 I2C_ADDR1, F18 PWR_BRAKE#, H19 JTAG_SEL and F20–K20 JTAG: LOW/MEDIUM → HIGH pin identity / MEDIUM electrical treatment, with 1.8 V levels noted.
- Connector A K18 PWR_EN and K19 THERM_OVERT#: added the specification's 1.8 V open-drain behaviour. The PWR_EN note flags that the known-working diode-fed 3.3 V treatment exceeds it.
- Connector A B7 and A39 (PRSNT2_A/PRSNT2_B in source columns): HIGH → DISPUTED. GND is retained pending review; the reference baseboard wires a presence-detect loop.
- Connector A J7: confirmed GND by the reference baseboard; noted that OpenPOWER's `INT_RST_N` at this position does not apply to SXM2.
- Connector A reserved contacts in rows 15–17: recorded the reference baseboard's `RSVD`/`RSVD_SNN` names and test-point-only treatment.
- Connector B H13/J34 PRSNT1_A/B and E34/F34 SMB_CLK/DAT: LOW/MEDIUM → HIGH pin identity / MEDIUM electrical treatment; candidate labels retained.
- Connector B E20/F20 NVHS_REFCLK: polarity confirmed by the reference baseboard.

The workbook, KiCad symbols and PDFs have not been regenerated for these note changes; their pin names are unaffected.

## 0.1.0-reference - 30 October 2026

First versioned reference snapshot, published as the initial public reference pre-release.

- Curated A/B pin maps covering 800 contacts per V100, with source/evidence fields and coordinate guidance.
- Two- and four-GPU NVLink tables and editable KiCad starters, using short net labels and a naming key. Every contact remains labelled; only NVLink data is connected.
- Standalone Catppuccin Mocha workbook, topology diagrams, schematic previews and native footprint image.
- Complete native schematic PDFs in Catppuccin Mocha and white-background monochrome print editions.
- Quick-start/download guidance, contribution and correction forms, and a citation file retaining upstream credits.
- CERN-OHL-W-2.0 for original hardware contributions and CC BY-SA 4.0 for original documentation/presentation, with separate upstream notices.

This release adds user guidance and exports to the existing mapping. No pin assignments or NVLink connections were changed while preparing it. Downloadable raw PCB footprints, routed boards and supporting power/clock circuits are not included; see [status](docs/status.md) and [footprint notes](docs/footprint.md).
