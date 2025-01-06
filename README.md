# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![Screenshot 2024-12-14 000135](https://github.com/user-attachments/assets/dbb131ec-cb31-45c9-88ac-faaebdc67f24)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![Screenshot 2024-12-14 000144](https://github.com/user-attachments/assets/39599268-d956-43f3-b7d8-6035e5871340)

![Screenshot 2024-12-14 000157](https://github.com/user-attachments/assets/593df924-e20a-496b-871b-78dd91a94807)

**Procedure**

/* write all the steps invloved */

**PROGRAM**
### Developed by: KABILAN P
### RegisterNumber:24900859
/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

 module RippleCounter(
   
   input wire clk,  // Clock input
   
   output reg [3:0] count // 4-bit counter output

);


// Counter logic

always @(posedge clk) begin

   if (count == 4'b1111) // Reset when count reaches 15
   
       count <= 4'b0000;

  else
      
       count <= count + 1; // Increment count

end

endmodule

// Testbench

module RippleCounter_tb;

// Inputs

reg clk;

// Outputs

wire [3:0] count;

// Instantiate the counter

RippleCounter uut(

   .clk(clk),
  
   .count(count)

);

// Clock generation

initial begin
   
   clk = 0;
   
   forever #5 clk = ~clk; // Toggle clock every 5 time units

end

// Stimulus

initial begin
   
   // Wait for a few clock cycles
  
   #10;   
   
   // Display header
   
   $display("Time | Count");
   
   $display("-----------------");

   // Functional table testing
   
   // Increment count 16 times and display the count
   
   repeat (16) begin
       
       #5; // Wait for one clock cycle
       
       $display("%4d | %b", $time, count);
   
   end
  
   // End simulation
  
   $finish;

end

endmodule

**RTL LOGIC FOR 4 Bit Ripple Counter**

![Screenshot 2024-12-14 000211](https://github.com/user-attachments/assets/cefa0761-4baa-4153-a8e2-ec319ff175f4)


**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

https://i.imgur.com/APGMqFU.jpeg


VM


**RESULT**

 Thus 4-BIT-RIPPLE-COUNTER is verified successfully.
