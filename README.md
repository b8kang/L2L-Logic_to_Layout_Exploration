# Repository Contents

This README explains what each file and folder contains.

---

## Circuit_and_Layout/

Artifacts for finalized standard-cell libraries (layouts + views).

- **CDL/**
  - `L2LAO.cdl` - Transistor-level netlists (CDL) for the **Area-Optimized** library.
  - `L2LMO.cdl` - Transistor-level netlists (CDL) for the **Metal-usage-Optimized** library.

- **GDS/**
  - `L2LAO.gds` - GDS layouts for **Area-Optimized** (L2LAO).
  - `L2LMO.gds` - GDS layouts for **Metal-usage-Optimized** (L2LMO).

- **physical_view/**
  - `L2LAO.lef` - LEF view (pins, blockages/OBS, geometry) for L2LAO.
  - `L2LMO.lef` - LEF view for L2LMO.

- **timing_power_view/**
  - `L2LAO_tt_0.7_25_nldm.lib` - Liberty (NLDM) @ TT/0.7V/25C for L2LAO.
  - `L2LMO_tt_0.7_25_nldm.lib` - Liberty (NLDM) @ TT/0.7V/25C for L2LMO.
  - `L2LAO_tt_0.7_25_nldm.db` - Compiled Liberty (.db) for Synopsys tools (L2LAO).
  - `L2LMO_tt_0.7_25_nldm.db` - Compiled Liberty (.db) for Synopsys tools (L2LMO).

- **cell_info/**
  - `cell_report` - Per-cell summary: Cell Name, f, #CPP, #M1/#M2 usage notes.

---

## Logic_to_Transistor_Network_Synthesis/

Summaries from transistor network synthesis under different stack bounds and input pools.

- **2stack_DP/**
  - `all_logs_summary.txt` - transistor network synthesis summary with stack height **M=2**, pool **DP** (Dual polarity).

- **2stack_Op/**
  - `all_logs_summary.txt` - transistor network synthesis summary with stack height **M=2**, pool **Op** (permutation-closed).

- **3stack_DP/**
  - `all_logs_summary.txt` - transistor network synthesis summary with **M=3**, pool **DP**.

- **3stack_Op/**
  - `all_logs_summary.txt` - transistor network synthesis summary with **M=3**, pool **Op**.

- **4stack_DP/**
  - `all_logs_summary.txt` - transistor network synthesis summary with **M=4**, pool **DP**.

- **4stack_Op/**
  - `all_logs_summary.txt` - transistor network synthesis summary with **M=4**, pool **Op**.

- **Grid_Scaffold/**
  - `logic_3input_P_CLASS_result_summary` - Synthesis summary for series-parallel-only runs (synthesis statistics).

---

## Notes

- **DP vs. Op**:  
  - **DP** = Dual Polarity (Primary and it's inversion).  
  - **Op** = permutation-closed pool (P-equivalent instantiations deduplicated).

- **Stack bound M**: maximum allowed series transistor count during PMOS synthesis.

- **CPP**: contact-poly-pitch, used as the basic area unit for layouts.

- **Full Detail Results** : We provide aggregate statistics for transistor-network synthesis in this repository. Detailed per-function artifacts including multiple optimal solutions and full solver log will be released after paper acceptance.
