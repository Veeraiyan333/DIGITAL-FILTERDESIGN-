# DIGITAL-FILTERDESIGN-

COMPANY :CODTECH IT SOLUTIONS

NAME :Veeraiyan D

INTERN ID :CT04DH908

DOMAIN: VLSI

DURATION: 4 WEEKS

MENTOR : NEELA SANTOSH


description:
Filter1 is verilog and Filter2 is teatbench runed by EDA playground.

A Finite Impulse Response (FIR) filter is one of the most commonly used digital filters in signal processing due to its simplicity, stability, and linear phase response. FIR filters produce an output that is a weighted sum of the current and a finite number of previous input samples. The weights applied to the samples are called filter coefficients, which define the behavior of the filter (e.g., low-pass, high-pass). In this design, a simple 4-tap FIR filter is implemented using Verilog, where each tap represents one delayed version of the input signal multiplied by a corresponding coefficient. The filter follows the equation:
y[n] = h0 * x[n] + h1 * x[n-1] + h2 * x[n-2] + h3 * x[n-3],
where x[n] is the current input sample and h0 to h3 are the filter coefficients.

The Verilog module fir_filter consists of input x (8-bit signed data), a clock signal clk, a reset signal, and the output y (16-bit signed data). Four coefficients are defined as parameters: h0=1, h1=2, h2=2, and h3=1, representing a simple moving average-like filter. To store the current and previous input samples, four registers (x_reg0 to x_reg3) are used as shift registers. On every positive edge of the clock, the input sample shifts through the registers, ensuring that the filter always has access to the current and the last three samples. The filter output y is computed by performing the multiply-accumulate operation on these samples with the respective coefficients. When the reset signal is high, all registers and output are cleared to zero.

The testbench tb_fir_filter verifies the design by providing a sequence of input samples while observing the output. A clock signal with a period of 10 ns is generated using always #5 clk = ~clk;. The $dumpfile and $dumpvars commands are used to generate a dump.vcd file that allows waveform viewing in EPWave on EDA Playground. The $monitor statement prints the current time, input value x, and filter output y during the simulation. The test sequence applies input values 1, 2, 3, 4, and 5 at 10 ns intervals, which helps observe the filter’s convolution behavior. Initially, as the pipeline of the filter fills up, the output grows with each sample until all taps contribute to the result.

output:

<img width="1360" height="634" alt="Image" src="https://github.com/user-attachments/assets/67ddd895-639c-4396-8b92-008622b09bc4" />


<img width="1362" height="635" alt="Image" src="https://github.com/user-attachments/assets/934f1dcb-1eaf-4ccd-b6d6-f774d066698b" />

