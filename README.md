# NASSCOM–VSD RISC-V based MYTH — My Workshop Notes & Lab Screenshots

Personal day-wise notes and lab screenshots from working through the **RISC-V based MYTH (Microprocessor for You in Thirty Hours)** program (NASSCOM / VSD, using the Redwood EDA / Makerchip curriculum). The structure of this repo is modeled on [chinmaya24163/NASSCOM-RISC-V-MYTH](https://github.com/chinmaya24163/NASSCOM-RISC-V-MYTH), which documents the same workshop — credit to that repo for the day-wise format.

All screenshots here are from my own run of the workshop VM (`riscv_workshop_collaterals`) and the Makerchip online IDE, captured while going through the lecture videos and labs over a few study sessions.

## What the workshop covers

- RISC-V ISA fundamentals and the GNU compiler toolchain
- C-to-assembly compilation, disassembly, and Spike simulation
- Signed/unsigned number representation
- The Application Binary Interface (ABI) and register naming
- Basic verification flow for a RISC-V program (iverilog / testbench)
- Digital logic design in TL-Verilog using the Makerchip IDE
- Combinational, sequential, and pipelined logic; validity (`$valid`)
- Single-cycle RISC-V CPU micro-architecture (fetch, decode, register file, ALU, branches)
- Converting the single-cycle core into a pipelined core and resolving hazards
- Load/store and jump instructions, completing a working pipelined RV32I core

> **Note on organization:** screenshots are grouped below by day of the curriculum, following the topic each screenshot shows. Since these were captured while watching the lecture recordings across a few sessions (rather than tagged lab-by-lab as I went), the grouping is close but approximate — feel free to re-sort images within a day if you spot one that belongs earlier/later.

---

## Repository structure

```
.
├── README.md
├── day1/images/   (86 screenshots) — RISC-V ISA & GNU toolchain
├── day2/images/   (27 screenshots) — ABI & basic verification flow
├── day3/images/   (27 screenshots) — TL-Verilog & Makerchip digital logic
├── day4/images/   (11 screenshots) — Single-cycle RISC-V CPU micro-architecture
└── day5/images/   (11 screenshots) — Complete pipelined RISC-V CPU
```

---

## RV Day 1 — Introduction to RISC-V ISA and GNU compiler toolchain

- Introduction to RISC-V, and how applications map down to hardware
- Course roadmap / content overview
- Lab: C program to compute the sum from 1 to N
- Lab: RISC-V GCC compile and disassemble (`riscv64-unknown-elf-gcc`, `objdump`)
- Lab: Spike simulation and debug (`spike pk`, `spike -d`)
- Unsigned and signed number representation (8/16/32/64-bit ranges)
- Lab: programs to find the highest/lowest representable signed and unsigned numbers

<details>
<summary><b>Show 86 screenshots</b></summary>

<img src="day1/images/01.png" width="700"><br>
<img src="day1/images/02.png" width="700"><br>
<img src="day1/images/03.png" width="700"><br>
<img src="day1/images/04.png" width="700"><br>
<img src="day1/images/05.png" width="700"><br>
<img src="day1/images/06.png" width="700"><br>
<img src="day1/images/07.png" width="700"><br>
<img src="day1/images/08.png" width="700"><br>
<img src="day1/images/09.png" width="700"><br>
<img src="day1/images/10.png" width="700"><br>
<img src="day1/images/11.png" width="700"><br>
<img src="day1/images/12.png" width="700"><br>
<img src="day1/images/13.png" width="700"><br>
<img src="day1/images/14.png" width="700"><br>
<img src="day1/images/15.png" width="700"><br>
<img src="day1/images/16.png" width="700"><br>
<img src="day1/images/17.png" width="700"><br>
<img src="day1/images/18.png" width="700"><br>
<img src="day1/images/19.png" width="700"><br>
<img src="day1/images/20.png" width="700"><br>
<img src="day1/images/21.png" width="700"><br>
<img src="day1/images/22.png" width="700"><br>
<img src="day1/images/23.png" width="700"><br>
<img src="day1/images/24.png" width="700"><br>
<img src="day1/images/25.png" width="700"><br>
<img src="day1/images/26.png" width="700"><br>
<img src="day1/images/27.png" width="700"><br>
<img src="day1/images/28.png" width="700"><br>
<img src="day1/images/29.png" width="700"><br>
<img src="day1/images/30.png" width="700"><br>
<img src="day1/images/31.png" width="700"><br>
<img src="day1/images/32.png" width="700"><br>
<img src="day1/images/33.png" width="700"><br>
<img src="day1/images/34.png" width="700"><br>
<img src="day1/images/35.png" width="700"><br>
<img src="day1/images/36.png" width="700"><br>
<img src="day1/images/37.png" width="700"><br>
<img src="day1/images/38.png" width="700"><br>
<img src="day1/images/39.png" width="700"><br>
<img src="day1/images/40.png" width="700"><br>
<img src="day1/images/41.png" width="700"><br>
<img src="day1/images/42.png" width="700"><br>
<img src="day1/images/43.png" width="700"><br>
<img src="day1/images/44.png" width="700"><br>
<img src="day1/images/45.png" width="700"><br>
<img src="day1/images/46.png" width="700"><br>
<img src="day1/images/47.png" width="700"><br>
<img src="day1/images/48.png" width="700"><br>
<img src="day1/images/49.png" width="700"><br>
<img src="day1/images/50.png" width="700"><br>
<img src="day1/images/51.png" width="700"><br>
<img src="day1/images/52.png" width="700"><br>
<img src="day1/images/53.png" width="700"><br>
<img src="day1/images/54.png" width="700"><br>
<img src="day1/images/55.png" width="700"><br>
<img src="day1/images/56.png" width="700"><br>
<img src="day1/images/57.png" width="700"><br>
<img src="day1/images/58.png" width="700"><br>
<img src="day1/images/59.png" width="700"><br>
<img src="day1/images/60.png" width="700"><br>
<img src="day1/images/61.png" width="700"><br>
<img src="day1/images/62.png" width="700"><br>
<img src="day1/images/63.png" width="700"><br>
<img src="day1/images/64.png" width="700"><br>
<img src="day1/images/65.png" width="700"><br>
<img src="day1/images/66.png" width="700"><br>
<img src="day1/images/67.png" width="700"><br>
<img src="day1/images/68.png" width="700"><br>
<img src="day1/images/69.png" width="700"><br>
<img src="day1/images/70.png" width="700"><br>
<img src="day1/images/71.png" width="700"><br>
<img src="day1/images/72.png" width="700"><br>
<img src="day1/images/73.png" width="700"><br>
<img src="day1/images/74.png" width="700"><br>
<img src="day1/images/75.png" width="700"><br>
<img src="day1/images/76.png" width="700"><br>
<img src="day1/images/77.png" width="700"><br>
<img src="day1/images/78.png" width="700"><br>
<img src="day1/images/79.png" width="700"><br>
<img src="day1/images/80.png" width="700"><br>
<img src="day1/images/81.png" width="700"><br>
<img src="day1/images/82.png" width="700"><br>
<img src="day1/images/83.png" width="700"><br>
<img src="day1/images/84.png" width="700"><br>
<img src="day1/images/85.png" width="700"><br>
<img src="day1/images/86.png" width="700"><br>

</details>

---

## RV Day 2 — Application Binary Interface (ABI) and basic verification flow

- Introduction to the ABI: registers, XLEN, and ABI names (`x0`–`x31`)
- Memory allocation for double words; load/add/store instruction examples
- I-type / R-type / S-type instruction encoding
- Lab: rewriting the sum-1-to-N program using function calls in assembly
- Lab: reviewing and simulating the ASM function call
- Basic verification flow: running a compiled program on a RISC-V CPU (`picorv32.v`, `testbench.v`)

<details>
<summary><b>Show 27 screenshots</b></summary>

<img src="day2/images/01.png" width="700"><br>
<img src="day2/images/02.png" width="700"><br>
<img src="day2/images/03.png" width="700"><br>
<img src="day2/images/04.png" width="700"><br>
<img src="day2/images/05.png" width="700"><br>
<img src="day2/images/06.png" width="700"><br>
<img src="day2/images/07.png" width="700"><br>
<img src="day2/images/08.png" width="700"><br>
<img src="day2/images/09.png" width="700"><br>
<img src="day2/images/10.png" width="700"><br>
<img src="day2/images/11.png" width="700"><br>
<img src="day2/images/12.png" width="700"><br>
<img src="day2/images/13.png" width="700"><br>
<img src="day2/images/14.png" width="700"><br>
<img src="day2/images/15.png" width="700"><br>
<img src="day2/images/16.png" width="700"><br>
<img src="day2/images/17.png" width="700"><br>
<img src="day2/images/18.png" width="700"><br>
<img src="day2/images/19.png" width="700"><br>
<img src="day2/images/20.png" width="700"><br>
<img src="day2/images/21.png" width="700"><br>
<img src="day2/images/22.png" width="700"><br>
<img src="day2/images/23.png" width="700"><br>
<img src="day2/images/24.png" width="700"><br>
<img src="day2/images/25.png" width="700"><br>
<img src="day2/images/26.png" width="700"><br>
<img src="day2/images/27.png" width="700"><br>

</details>

---

## RV Day 3 — Digital logic design with TL-Verilog and Makerchip

- Introduction to logic gates and the Makerchip online IDE (makerchip.com)
- Lab: Makerchip platform walkthrough (editor / diagram / waveform panes)
- Lab: combinational logic — a 4-function calculator in TL-Verilog
- Sequential logic, counters, and a sequential calculator lab
- Pipelining concepts: timing, the waterfall/pipeline diagram, pipeline calculator lab
- Validity (`$valid`) and using it to flag/handle invalid pipeline cycles
- Hierarchy in TL-Verilog

<details>
<summary><b>Show 27 screenshots</b></summary>

<img src="day3/images/01.png" width="700"><br>
<img src="day3/images/02.png" width="700"><br>
<img src="day3/images/03.png" width="700"><br>
<img src="day3/images/04.png" width="700"><br>
<img src="day3/images/05.png" width="700"><br>
<img src="day3/images/06.png" width="700"><br>
<img src="day3/images/07.png" width="700"><br>
<img src="day3/images/08.png" width="700"><br>
<img src="day3/images/09.png" width="700"><br>
<img src="day3/images/10.png" width="700"><br>
<img src="day3/images/11.png" width="700"><br>
<img src="day3/images/12.png" width="700"><br>
<img src="day3/images/13.png" width="700"><br>
<img src="day3/images/14.png" width="700"><br>
<img src="day3/images/15.png" width="700"><br>
<img src="day3/images/16.png" width="700"><br>
<img src="day3/images/17.png" width="700"><br>
<img src="day3/images/18.png" width="700"><br>
<img src="day3/images/19.png" width="700"><br>
<img src="day3/images/20.png" width="700"><br>
<img src="day3/images/21.png" width="700"><br>
<img src="day3/images/22.png" width="700"><br>
<img src="day3/images/23.png" width="700"><br>
<img src="day3/images/24.png" width="700"><br>
<img src="day3/images/25.png" width="700"><br>
<img src="day3/images/26.png" width="700"><br>
<img src="day3/images/27.png" width="700"><br>

</details>

---

## RV Day 4 — Basic RISC-V CPU micro-architecture

- Single-cycle RISC-V CPU architecture overview (PC, Dec, RF, ALU, memory)
- Lab: program counter (PC) logic
- Lab: instruction fetch logic
- Lab: instruction decode for R/I/S/B/U/J instruction types, immediate decode
- Lab: register file read/write; ALU for `add`/`addi`
- Lab: implementing branch instructions
- Lab: simple testbench for the CPU

<details>
<summary><b>Show 11 screenshots</b></summary>

<img src="day4/images/01.png" width="700"><br>
<img src="day4/images/02.png" width="700"><br>
<img src="day4/images/03.png" width="700"><br>
<img src="day4/images/04.png" width="700"><br>
<img src="day4/images/05.png" width="700"><br>
<img src="day4/images/06.png" width="700"><br>
<img src="day4/images/07.png" width="700"><br>
<img src="day4/images/08.png" width="700"><br>
<img src="day4/images/09.png" width="700"><br>
<img src="day4/images/10.png" width="700"><br>
<img src="day4/images/11.png" width="700"><br>

</details>

---

## RV Day 5 — Complete pipelined RISC-V CPU micro-architecture

- Control-flow hazards and read-after-write (RAW) hazards
- Pipelining the CPU: `$valid` signal, distributing logic across pipeline stages
- Lab: register file bypass to resolve RAW hazards
- Lab: correcting the branch target path
- Lab: completing instruction decode (excluding fence/ecall/ebreak) and the ALU
- Lab: load/store instructions, instantiating data memory
- Lab: jump instructions (JAL/JALR) and wrap-up

<details>
<summary><b>Show 11 screenshots</b></summary>

<img src="day5/images/01.png" width="700"><br>
<img src="day5/images/02.png" width="700"><br>
<img src="day5/images/03.png" width="700"><br>
<img src="day5/images/04.png" width="700"><br>
<img src="day5/images/05.png" width="700"><br>
<img src="day5/images/06.png" width="700"><br>
<img src="day5/images/07.png" width="700"><br>
<img src="day5/images/08.png" width="700"><br>
<img src="day5/images/09.png" width="700"><br>
<img src="day5/images/10.png" width="700"><br>
<img src="day5/images/11.png" width="700"><br>

</details>

---

## Environment / tools used

- Ubuntu VM (`riscv_workshop_collaterals`) provided for the workshop, run in VirtualBox
- `riscv64-unknown-elf-gcc` toolchain, `spike` ISA simulator, `objdump`
- `iverilog` for RTL simulation, with `picorv32.v` / `testbench.v` from the workshop labs
- [Makerchip](https://makerchip.com) online IDE with TL-Verilog (SandPiper compiler) for the RTL labs

## Credits

- Workshop: RISC-V based MYTH, NASSCOM / VLSI System Design (VSD), delivered with Redwood EDA / Makerchip material
- Repo structure inspired by [chinmaya24163/NASSCOM-RISC-V-MYTH](https://github.com/chinmaya24163/NASSCOM-RISC-V-MYTH)
