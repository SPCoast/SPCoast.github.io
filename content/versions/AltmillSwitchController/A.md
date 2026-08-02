---
iskicad: true
sidebar: spcoast_sidebar
project: AltmillSwitchController
title: A
date: '2026-08-02T03:49:24+00:00'
issue_date: '2025-12-03'
design_rev: A
board_rev: A
designer: ''
tagline: ''
overview: ''
company: SPCoast
tags:
- SPCoast
- kicad
status: active
publish: true
image_path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.thumbnail.png
images:
- image_path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.top.png
  title: Top
- image_path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.bottom.png
  title: Bottom
- image_path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.sch.svg
  title: Schematic
artifacts:
- path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.sch.pdf
  tag: schematic-pdf
  type: download
  post: Full schematic (all sheets)
- path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.ibom.html
  tag: interactive-bom
  type: download
  post: Interactive HTML BOM
- path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.step
  tag: step-model
  type: download
  post: 3D STEP model
- path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.fab.zip
  tag: fab-pack
  type: download
  post: Fab-house bundle (BOM + POS + gerbers)
- path: /versions/AltmillSwitchController/A/AltmillSwitchController-A.source.zip
  tag: source-archive
  type: download
  post: KiCad source archive
github_url: https://github.com/plocher/AltmillSwitchController
kproj_publish_context:
  schema: 2
  kproj_version: 0.13.2
  kicad_cli_version: 10.0.1
  inventory_enabled: true
  fabricator: jlc
  ibom_extra_fields:
  - Details
  - Description
  kproj_install_type: release
  watermark: ''
audit:
  errors: 0
  warnings: 3
drc:
  errors: 0
  warnings: 0
  exclusions: 0
erc:
  errors: 0
  warnings: 0
  exclusions: 0
libraries:
  internal: []
  external: []
  ambiguous:
  - Capacitor_SMD
  - Device
  - Diode
  - Isolator
  - Package_DIP
  - Package_TO_SOT_SMD
  - SPCoast
  - Switch
  - TerminalBlock_Phoenix
  - power
library_inventory:
  symbol:
    kicad:
    - power
    added: []
    unknown:
    - Device
    - Diode
    - Isolator
    - SPCoast
    - Switch
  footprint:
    kicad: []
    added: []
    unknown:
    - Capacitor_SMD
    - Package_DIP
    - Package_TO_SOT_SMD
    - SPCoast
    - TerminalBlock_Phoenix
---
## Metadata Audit

| Severity | Rule | Value | Reason |
|----------|------|-------|--------|
| warning | pcb_titleblock_empty |  | PCB has an empty or missing (title_block ...) stanza |
| warning | comment9_missing |  | ${COMMENT9} (status) is empty or absent on both SCH and PCB; defaulting to status=active for this publish |
| warning | date_format | 2025-12-03 | date '2025-12-03' does not match the locked YYYY.MM format |

## DRC / ERC Findings

| Severity | Source | Type | Location | Message |
|----------|--------|------|----------|----------|
| | | | | _No DRC/ERC findings._ |
