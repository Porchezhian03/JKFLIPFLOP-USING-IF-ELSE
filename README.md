JKFLIPFLOP-USING-IF-ELSE
AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![300541519-a649c30b-232b-4558-b188-fd6c09845180](https://github.com/user-attachments/assets/ae29575c-241b-4439-95d5-362a12eff051)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![300541618-c4360742-e8a8-4937-b089-c46c0433f9a3](https://github.com/user-attachments/assets/d4bdc808-1d15-4f5b-9990-30ce1692346e)


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

![300541696-6c275261-a6d5-4c37-a3a7-1e88ca11c4cd](https://github.com/user-attachments/assets/a62bfbd2-2d92-4758-b327-bd631e924c42)


By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![300541801-5174f41b-0ce0-4329-a372-6d1943ea6673](https://github.com/user-attachments/assets/5564b92f-8700-4d4d-a634-ee2d785243f1)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

Procedure

/* write all the steps invloved */

PROGRAM module de7(j, k, clk, rst, q); input j, k, clk, rst; output reg q;

always @(posedge clk or posedge rst) begin if (rst) q <= 0; else if (j == 0 && k == 0) q <= q; else if (j == 0 && k == 1) q <= 0; else if (j == 1 && k == 0) q <= 1; else if (j == 1 && k == 1) q <= ~q; end endmodule /* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by: porchezhian E
RegisterNumber:24001347 */

RTL LOGIC FOR FLIPFLOPS

![391906169-1ce7d636-c187-4532-a0ae-134a8f6c7d34](https://github.com/user-attachments/assets/02bc14c1-5625-4361-880f-e61153ebc177)


TIMING DIGRAMS FOR FLIP FLOPS

![391906221-db6cb0c3-ebce-447b-9acc-18cbdce42d95](https://github.com/user-attachments/assets/21f5d315-ee7d-4e7e-ab01-e00f10c4ec3b)


RESULTS Program for JK flipflops was verified in quartus using Verilog programming

