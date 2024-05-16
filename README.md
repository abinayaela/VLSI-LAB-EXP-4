# VLSI-LAB-EXP-4
SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

## AIM

To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Vivado 2023.


## APPARATUS REQUIRED

vivado 2023.2
## PROCEDURE

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

## LOGIC DIAGRAM

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)
## VERILOG CODE
module SR(clk,s,r,rst,q );

input s,r,clk,rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({s,r})

2'b00: q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=1'bx;

endcase

end

end

endmodule
## OUTPUT
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/ddd9ed17-37dd-478e-8241-f58b838c615a)

JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)
## VERILOG CODE
module jk(j,k,clk,rst,Q);

input j,k,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=0;

else

begin

case({j,k})

2'b00:Q=Q;

2'b01:Q=0;

2'b10:Q=1;

2'b11:Q=~Q;

endcase

end

end

endmodule
## OUTPUT
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/970b020a-d796-436a-92c3-d148c22d1afd)


T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)
## VERILOG CODE
module tff(t,clk,rst,Q);

input t,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else if(t==0)

Q=Q;

else

Q=~Q;

end

endmodule
## OUTPUT
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/483ae144-b786-41ff-bc08-759148715d72)


D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)
## VERILOG CODE
module dff(d,clk,rst,Q);

input d,clk,rst;

output reg Q;

always @(posedge clk)

begin

if(rst==1)

Q=1'b0;

else

Q=d;

end

endmodule
## OUTPUT
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/bd96751e-c1f1-408b-a9a9-a34c78255849)


COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)
## MOD 10
module updown(clk,rst,out);

input clk,rst;

output reg[3:0]out;

always@(posedge clk)

begin

if(rst==1 | out==4'b1001)

out=4'b0000;

else

out=out+1'b1;

end

endmodule
## OUTPUT
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/737f3e47-f65d-4d08-9746-2c0e678619af)
## 4 BIT UPDOWN
module updown(clk,rst,updown,out);

input clk,rst,updown;

output reg[3:0]out;

always@(posedge clk)

begin

if(rst==1)

out=4'b0000;

else

if(updaown==1)

out=out+1'b1;

else

out=out-1'b1;

end

endmodule
## OUTPUT
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/488a90fc-aaa6-4db8-9042-f757488b43c2)
## RIPPLE CARRY
module ripplecounter(clk,rst,q);

input clk,rst;

output [3:0]q;

tff tff1(q[0],clk,rst);

tff tff2(q[1],q[0],rst);

tff tff3(q[2],q[1],rst);

tff tff4(q[3],q[2],rst);

endmodule

module tff(q,clk,rst);

input clk,rst;

output q;

wire d;

dff df1(q,d,clk,rst);

not n1(d,q);

endmodule

module dff(q,d,clk,rst);

input d,clk,rst;

output q;

reg q;

always@(posedge clk or posedge rst)

begin

if(rst)

q=1'b10;

else

q=d;

end

endmodule
## OUTPUT
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/d9c643bb-53bc-410e-81be-35d8d7bd2126)

## RESULT
Thus the simulation and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Vivado 2023. was successfully exectued and verified.

