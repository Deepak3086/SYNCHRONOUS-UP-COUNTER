### NAME: DEEPAK J G 
### REG NO: 24901065
# EXP-7: IMPLEMENTATION OF SYNCHRONUS UP COUNTER
# AIM:

To implement 4 bit synchronous up counter and validate functionality.

# SOFTWARE REQUIRED:

Quartus prime

# THEORY

When counter is clocked such that each flip-flop in the counter is triggered at the same time , the counter is called synchronous counter.

*4 bit synchronous UP Counter*

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

# PROCEDURE:

1. Type the program in Quartus software.

2. Compile and run the program.

3. Generate the RTL schematic and save the logic diagram.

4. Create nodes for inputs and outputs to generate the timing diagram.

5. For different input combinations generate the timing diagram.

# PROGRAM
~~~

module ex11(out,clk,rstn);
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
~~~

# RTL OUTPUT:

![Screenshot 2024-12-17 192123](https://github.com/user-attachments/assets/d64a28b2-0c7d-484c-80e9-d449936fc3fc)

# OUTPUT DIAGRAM:

![waveform](https://github.com/user-attachments/assets/77411d3c-9c86-4bf8-b7d9-ea0be1e3a186)


# RESULT

The Synchronous Up Counter was implemented successfully using Verilog, and its functionality was validated through simulation. The output matches the expected functional table of the Synchronous Up Counter.
