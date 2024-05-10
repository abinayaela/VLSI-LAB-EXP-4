# VLSI-LAB-EXP-4
SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

AIM: 
To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Vivado 2023.


APPARATUS REQUIRED:

vivado 2023.2

**LOGIC DIAGRAM**

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)


JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)


D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)


COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)


  
PROCEDURE:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.


**VERILOG CODE**

**SR FLIPFLOP**

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

JK FLIPFLOP

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

T FLIPFLOP

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

D FLIPFLOP

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

MOD 10 COUNER

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

4bit UPDOWN COUNER

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

RIPPLE CARRY COUNER

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




OUTPUT WAVEFORM
 SR FLIPFLOP
 ![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/467e0210-b948-4a7a-bce2-126b9c76eadc)
jk FLIPFLOP
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/9a258192-2ba3-4874-a3ad-7d09f63fc232)
T FLIPFLOP
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/742ef8e6-058d-472b-ae7e-ed352c093195)
D FLIPFLOP
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/33a6f7f9-b435-416a-b430-9e5ae876211f)
MOD 10 COUNER
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/f1c29577-1107-45a8-8e98-17489151e728)
4bit UPDOWN COUNTER
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/56e7efeb-94b3-40da-b085-0d0487146dbd)
RIPPLE CARRY COUNTER
![image](https://github.com/abinayaela/VLSI-LAB-EXP-4/assets/164911294/36aa116e-2138-4a09-a17c-1afd46c80858)


RESULT
Thus the simulation and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Vivado 2023. was successfully exectued and verified.

