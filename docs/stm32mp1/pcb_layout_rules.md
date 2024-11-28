# Memory Layout Rules for LPDDR3 (AN5122)

## Data Signal Rules for LPDDR3

### Byte Groups (32-bit Interface)
- **Byte0:** DQ[7:0], DQM0, DQS0_N, DQS0_P
- **Byte1:** DQ[15:8], DQM1, DQS1_N, DQS1_P
- **Byte2:** DQ[23:16], DQM2, DQS2_N, DQS2_P
- **Byte3:** DQ[31:24], DQM3, DQS3_N, DQS3_P

### Byte Groups (16-bit Interface)
- **Byte0:** DQ[7:0], DQM0, DQS0_N, DQS0_P
- **Byte1:** DQ[15:8], DQM1, DQS1_N, DQS1_P

### Routing Rules
- Route data signals on the **top PCB layer** wherever possible.
- Use **S-3S isolation** as a minimum; optimize to S-2S or S-1.5S if necessary. Keep **S-1S segments as short as possible**.

### Length Matching
- **DQ or DQM to DQS_N/DQS_P:** ±40 mils (1.016 mm)
- **DQS_N/DQS_P relative to CLK_N/CLK_P:** Must be **0 to 590 mils (14.986 mm) shorter** than CLK_N/CLK_P.
- **CLK_N/CLK_P:** Must be the **longest traces**.

---

## Address and Control (A/C) Signal Rules

### Routing Rules
- Use the **PCB bottom layer** for A/C distribution to memory devices.
- The **top layer** should only be used for stubs and A/C bus crossings.
- Follow the **S-3S isolation rule** wherever possible; optimize to S-2S or S-1.5S if needed. Minimize **S-1S segments**.

### Length Matching
- **A/C signals:** Must be **0 to 40 mils (1.016 mm) shorter** than CLK_N/CLK_P.
- **CLK_N/CLK_P maximum length:** 4.72 inches (12 cm).

---

## ZQ Signal Rules
- Keep the trace to the reference resistor **as short as possible**.
- Ensure good isolation from noisy signals.

---

## General Notes
- **Trace length:** `substrate length + via length + board track length`
- Refer to ST reference designs for:
  - Signal ordering
  - BGA fan-out
  - Layout examples
