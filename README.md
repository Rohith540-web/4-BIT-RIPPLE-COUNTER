# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */

**PROGRAM**

```
module ripple_counter (
    input clk,       
    input rst,        
    output [3:0] count  
);


    reg q0, q1, q2, q3;
    
   
    always @(posedge clk or posedge rst) begin
        if (rst) begin
           
            q0 <= 0;
            q1 <= 0;
            q2 <= 0;
            q3 <= 0;
        end else begin
           
            q0 <= ~q0; 
            q1 <= q0 ? ~q1 : q1; 
            q2 <= q1 ? ~q2 : q2; 
            q3 <= q2 ? ~q3 : q3; 
        end
    end

   
    assign count = {q3, q2, q1, q0}; 

endmodule

```
 Developed by:Rohith V, RegisterNumber:24900447


**RTL LOGIC FOR 4 Bit Ripple Counter**

![Screenshot 2024-12-16 204534](https://github.com/user-attachments/assets/ddca352d-d138-4a05-8be4-917fb8665865)

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

![Screenshot (67)](https://github.com/user-attachments/assets/104472a3-916f-479d-9efa-e40a4fdd80eb)


**RESULTS**
Implementation of  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables
