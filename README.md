JKFLIPFLOP-USING-IF-ELSE
AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

image

This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

image

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

image

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

image

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

Procedure

/* write all the steps invloved */

PROGRAM module de7(j, k, clk, rst, q); input j, k, clk, rst; output reg q;

always @(posedge clk or posedge rst) begin if (rst) q <= 0; else if (j == 0 && k == 0) q <= q; else if (j == 0 && k == 1) q <= 0; else if (j == 1 && k == 0) q <= 1; else if (j == 1 && k == 1) q <= ~q; end endmodule /* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by: porchezhian E
RegisterNumber:24001347 */

RTL LOGIC FOR FLIPFLOPS Screenshot 2024-12-03 145702 TIMING DIGRAMS FOR FLIP FLOPS Screenshot 2024-12-03 150102

RESULTS Program for JK flipflops was verified in quartus using Verilog programming

