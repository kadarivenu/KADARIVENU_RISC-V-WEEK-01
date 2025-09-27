# Day 2 Summary: Timing Libraries, Synthesis Approaches, and Flip-Flop Coding

Day 2 of the RTL Workshop expanded on the foundations of Day 1 by introducing **timing awareness, synthesis strategies, and best practices in sequential logic design**. These concepts are essential for writing synthesizable RTL that works reliably in real hardware.

---

## 📘 Key Topics Covered

### 🔹 Timing Libraries and the SKY130 PDK

* Explored the **SKY130 timing library** and `.lib` file format.
* Learned how `.lib` files provide detailed information on:

  * Gate delays, setup/hold times, and clock-to-Q timing.
  * Power consumption and drive strength options.
  * Variants of gates optimized for **speed, area, or power**.
* Understood why timing libraries are the backbone of accurate **synthesis and static timing analysis (STA)**.

---

### 🔹 Synthesis Approaches: Hierarchical vs Flattened

* **Hierarchical Synthesis**

  * Maintains module boundaries.
  * Easier to debug and re-use modules.
  * Faster synthesis for **large-scale systems**.

* **Flattened Synthesis**

  * Collapses all modules into one netlist.
  * Allows **aggressive optimizations** across module boundaries.
  * Can improve performance but increases complexity.

💡 *Designers often use a hybrid approach: keep hierarchy for top-level readability and flatten critical sub-modules for optimization.*

---

### 🔹 Flip-Flop RTL Coding Styles

* Discussed **efficient and synthesizable flip-flop coding** techniques.
* Explored variations of **reset and set behavior**:

  * **Asynchronous reset/set:** Immediate effect independent of the clock.
  * **Synchronous reset:** Triggered only on clock edge, more predictable in synthesis.
* Demonstrated Verilog templates for:

  * D Flip-Flop with asynchronous reset.
  * D Flip-Flop with synchronous reset.
  * D Flip-Flop with enable (clock gating alternative).

💡 *Coding style matters!* Poor flip-flop coding can lead to synthesis-simulation mismatches or inefficient gate mapping.

---

### 🔹 Simulation & Waveform Debugging

* Continued using **Icarus Verilog (iverilog)** for simulation.
* Verified flip-flop behavior using **testbenches and waveform analysis in GTKWave**.
* Emphasized the importance of initializing inputs and covering edge cases in testbenches.

---

### 🔹 Synthesis with Yosys

* Recap of Yosys synthesis flow:

  1. Load `.lib` timing library.
  2. Read Verilog design.
  3. Run `synth` for RTL-to-gate-lev
