# SR_FLIPFLOP

AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

image

This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

image

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

image

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

image

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

#Procedure


Procedure to design SR Flip-Flop (5 lines):


Identify the inputs S (Set), R (Reset), Clock, and output Q.


Use a basic SR latch and add a clock signal to control state changes.


Write the truth table defining the behavior for all combinations of S and R.


Implement the logic using gates or HDL so output changes only on the active clock edge.


Verify the design by simulation and check all valid and invalid input conditions.



#PROGRAM

```
Flip flop
-------------------------------------------------
// SR Flip-Flop (with async reset)
module sr_ff (
    input  wire clk, rst, S, R,
    output reg  Q
);
    always @(posedge clk) begin
        if (rst)
            Q <= 1'b0;         // Reset
        else begin
            case ({S,R})
                2'b00: Q <= Q;     // No change
                2'b01: Q <= 1'b0;  // Reset
                2'b10: Q <= 1'b1;  // Set
                2'b11: Q <= 1'bx;  // Invalid
            endcase
        end
    end
endmodule
```
Developed by:25013590

RegisterNumber: VANATHI T

RTL LOGIC FOR FLIPFLOPS
<img width="1920" height="1020" alt="Screenshot 2025-12-14 201749" src="https://github.com/user-attachments/assets/06ab1552-98f7-45d4-afe2-476fe5dda508" />

TIMING DIGRAMS FOR FLIP FLOPS

RESULTS
