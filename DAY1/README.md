# Day 1: Introduction to Verilog RTL Design & Synthesis

Welcome to **Day 1 of the RTL Workshop!**
Today begins your journey into digital hardware design with **Verilog HDL**, open-source simulation, and logic synthesis using tools like *Icarus Verilog* and *Yosys*. The goal of this session is to build a solid foundation in RTL design through **hands-on labs, real-world examples, and essential theory**.

---

## 📑 Table of Contents

1. What is a Simulator, Design, and Testbench?
2. Getting Started with Icarus Verilog (iverilog)
3. Lab: Simulating a 2-to-1 Multiplexer
4. Verilog Code Analysis
5. Introduction to Yosys & Gate Libraries
6. Synthesis Lab with Yosys
7. Common Pitfalls & Debugging Tips
8. Summary & Takeaways

---

## 🖥 What is a Simulator, Design, and Testbench?

* **Simulator:** Software that validates the functionality of digital circuits by applying test inputs and observing outputs. (e.g., *iverilog + gtkwave*).
* **Design:** Your Verilog RTL description of the logic (e.g., multiplexer, adder, flip-flop).
* **Testbench:** A non-synthesizable environment that drives stimulus to the design and verifies expected outputs.

💡 **Key Note:** Testbenches are like "virtual labs" that help catch errors before hardware implementation.

---

## ⚙️ Getting Started with Icarus Verilog (iverilog)

*Icarus Verilog* is a free, open-source simulator widely used in academic and hobbyist projects. The flow generally includes:

1. **Write** your design and testbench in Verilog.
2. **Compile** them using `iverilog`.
3. **Run** the compiled simulation.
4. **View waveforms** using GTKWave for debugging.

👉 Pro Tip: Always separate design and testbench files for clarity and reusability.

---

## 🔬 Lab: Simulating a 2-to-1 Multiplexer

Steps:

1. Clone this repository.
2. Ensure tools (*iverilog*, *gtkwave*) are installed.
3. Compile design and testbench:

   ```bash
   iverilog -o mux_tb.vvp mux.v mux_tb.v
   vvp mux_tb.vvp
   ```
4. View waveform:

   ```bash
   gtkwave mux_tb.vcd
   ```

📈 You should observe the multiplexer selecting between inputs `i0` and `i1` based on `sel`.

---

## 📖 Verilog Code Analysis

Example: **2-to-1 Multiplexer**

* **Inputs:** `i0`, `i1`, `sel`
* **Output:** `y`
* **Logic:**

  * If `sel = 0`, output = `i0`
  * If `sel = 1`, output = `i1`

👉 This example introduces combinational logic design in Verilog.

---

## 🏗 Introduction to Yosys & Gate Libraries

* **Yosys** is an open-source synthesis tool that converts Verilog RTL to gate-level netlists.
* **Gate Libraries:** Collections of pre-designed gates (NAND, NOR, INV, DFF, etc.) with different variations optimized for:

  * Speed
  * Area
  * Power

💡 This helps designers make trade-offs depending on design constraints.

---

## 🔧 Synthesis Lab with Yosys

1. Load the Verilog design into Yosys.
2. Read the target gate library (e.g., *Sky130*).
3. Run synthesis using `synth`.
4. Perform technology mapping.
5. Export the netlist and visualize the synthesized circuit.

👉 Optional: Use `show` command in Yosys for schematic-level visualization.

---

## ⚠️ Common Pitfalls & Debugging Tips

* Forgetting to include testbench → simulation won't run.
* Misuse of blocking (`=`) vs non-blocking (`<=`) assignments → mismatches in sequential circuits.
* Not initializing inputs in testbench → unpredictable waveform outputs.
* Using unsupported constructs in synthesis → code may simulate but fail in synthesis.

---

## 📝 Summary & Takeaways

On **Day 1**, you have:

* Learned the roles of simulator, design, and testbench.
* Written and executed your **first Verilog simulation**.
* Viewed and analyzed waveforms in GTKWave.
* Explored the basics of Yosys and gate libraries.
* Performed **RTL-to-Gate-level synthesis** with Yosys.
* Understood common mistakes and how to debug effectively.

✅ This sets the foundation for exploring **timing, optimization, and advanced RTL design** in the upcoming days.

---

💡 *Remember: RTL design is both an art and a science. Practice small examples, analyze waveforms, and think like a digital circuit!*
