# INSTRUCTIONS-DESIGN-AND-SIMULATE-A-DIGITAL-FIR-FINITE-IMPULSE-RESPONSE-

"COMPANY": CODTECH IT SOLUTIONS

"NAME":CHALLAMBETI SRAVANTHI

"INTERN ID":CT06DG3299

"DOMAIN":VLSI

"DURATION":6 WEEKS

"MENTOR":NEELA SANTOSH

DESCRIPTION FOR TASK 4:

The objective of this project is to design a digital FIR (Finite Impulse Response) filter using the Verilog Hardware Description Language (HDL) and simulate it using industry-standard tools such as Xilinx Vivado. FIR filters are a class of digital filters with a finite number of coefficients and are widely used in digital signal processing (DSP) applications due to their inherent stability and linear phase characteristics.

What is an FIR Filter?

A Finite Impulse Response (FIR) filter produces an output based on a finite number of past input values. It performs a convolution between the input signal and the filter’s impulse response (the set of coefficients). The general form of an FIR filter output is given by:

y[n] = h[0]x[n] + h[1]x[n-1] + ... + h[N-1]x[n-(N-1)]

Where:

x[n] is the current input sample,

h[i] are the filter coefficients (impulse response),

y[n] is the output.


The FIR filter is non-recursive, meaning it does not use previous output values in its computation, which simplifies hardware implementation.


---

Task Overview

The core task involves:

1. Writing Verilog code to describe the FIR filter functionality.


2. Simulating the code using a testbench.


3. Verifying the functional correctness using a waveform viewer.


4. Analyzing the performance in terms of timing, stability, and correctness.



The FIR filter in this design is a 4-tap low-pass filter, with fixed coefficients resembling a smoothing kernel.

Verilog Module Description

The FIR filter Verilog module takes the following inputs and outputs:

Inputs:

clk: Clock signal to synchronize operations.

reset: Resets internal registers.

x_in: The 8-bit signed input sample.


Output:

y_out: The 16-bit signed filtered output.



Internally, the module uses:

A shift register (x[]) to store the latest 4 input samples.

A coefficient array (h[]) initialized using the initial block.

An always block triggered on the positive edge of the clock to shift inputs and compute the output.


This behavior closely mimics a real-time digital filter in hardware.

Tools and Platform Used

This design was created and simulated using the Xilinx Vivado Design Suite 2023.2. Vivado is a comprehensive FPGA development environment provided by Xilinx for writing, synthesizing, implementing, and simulating Verilog/VHDL designs.

Key Vivado Features Used:

Vivado Editor: To write and manage Verilog source files.

Simulation Tool (XSIM): For behavioral simulation of the Verilog code.

Waveform Viewer: To inspect signal transitions and verify output timing.


Operating System: Typically Vivado is run on Windows or Linux platforms. This specific task was done in a Linux Ubuntu environment, as shown in the screenshots, where simulation is being carried out interactively.


---

Simulation and Output Verification

The simulation includes writing a testbench that feeds input samples into the FIR filter module and monitors the output. The testbench generates a clock signal, applies reset, and inputs test vectors to validate the filter logic.

In the Vivado simulator, the user observes signals such as clk, reset, x_in, and y_out in the waveform viewer to verify:

Correct shifting of inputs.

Correct multiplication with coefficients.

Accurate summation for the final output.


Any errors in the output can be debugged by inspecting the timing and data flow in the simulation.


---

Applications

Digital FIR filters are used in:

Audio signal processing (equalizers, echo cancellation).

Image processing (smoothing, sharpening filters).

Communications (modulation/demodulation, channel filtering).

Biomedical devices (ECG signal filtering).

Radar and sonar systems.


Their stability, ease of implementation, and linear-phase response make FIR filters essential in real-time digital hardware systems, especially in FPGAs and ASICs.


---

Conclusion

This project demonstrates how to implement and simulate a digital FIR filter using Verilog. The Vivado design suite simplifies hardware design and simulation, providing powerful tools to visualize signal behavior. The design of such digital filters is crucial for modern embedded and DSP systems, bridging theory with practical hardware implementation.

