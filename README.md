### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */
Open Quartus software and create a new Verilog file. Paste the code and save it.
Compile the program to check for errors.
Generate the RTL schematic via the RTL Viewer and save the logic diagram.
Use the Waveform Editor to assign nodes for clk, rstn, and out.
Simulate the design with different clk and rstn combinations to generate the timing diagram, and save the results
**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:Carlton MAximus A RegisterNumber:25006709
*/module exp11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
	if(!rstn)
		out<=0;
	else
		out <= out+1;
end
endmodule

**RTL LOGIC UP COUNTER**
<img width="1003" height="403" alt="{98AD5EDB-8E35-40DD-8BCD-1F0A2E773317}" src="https://github.com/user-attachments/assets/fb245b99-a91a-4f14-bd75-beff4b37a739" />

**TIMING DIAGRAM FOR IP COUNTER**
<img width="1027" height="311" alt="{C1B4B68D-535F-4D5F-A199-1DE0BDF9A000}" src="https://github.com/user-attachments/assets/94f85024-22e0-460c-afed-a04efe7c01ba" />

**TRUTH TABLE**
<img width="658" height="335" alt="{E7B5469E-B162-4230-88B7-6699CE025D86}" src="https://github.com/user-attachments/assets/1022dbf0-0fce-48b6-ba09-2d5121d8953b" />

**RESULTS**
Thus the Synchronous 3 bit Up counter is implemeted and verified.

