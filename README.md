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

1.Open Quartus software and create a new Verilog file. Paste the code and save it.

2.Compile the program to check for errors.

3.Generate the RTL schematic via the RTL Viewer and save the logic diagram.

4.Use the Waveform Editor to assign nodes for clk, rstn, and out.

5.Simulate the design with different clk and rstn combinations to generate the timing diagram, and save the results.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
```
module exp11(out,clk,rstn);
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
```

Developed by: OBELESH R RegisterNumber: 24901123
*/

**RTL LOGIC UP COUNTER**
![Screenshot 2025-01-03 175913](https://github.com/user-attachments/assets/7097bee9-6b05-4764-bb78-e9758f57656c)

**TIMING DIAGRAM FOR IP COUNTER**
![Screenshot 2025-01-03 175925](https://github.com/user-attachments/assets/08a30d10-c0fb-44ad-9609-3ccc10c1eee1)

**TRUTH TABLE**
![Screenshot 2025-01-03 175943](https://github.com/user-attachments/assets/2e86c180-00b3-4fd5-9491-32e2c46b4033)

**RESULTS**
Thus the Synchronous 3 bit Up counter is implemeted and verified.
