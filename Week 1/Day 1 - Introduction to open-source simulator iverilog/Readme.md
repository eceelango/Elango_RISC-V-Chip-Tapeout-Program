# SKY130RTL D1SK1 L1 Introduction to iverilog design test bench

**Simulator**
+ Tool used for checking the functionality of the design
+ iVerilog is open source Verilog Simulator
+ Design: Represnted as a Verilog HDL
+ **TestBench:** Setup to apply stimulus to the design under test to check the functionality
+ **Simulator:** Looks fo rchanges the in the input accordingly the output will be evaluated

## Testbench Environment:
<img width="1017" height="282" alt="tb_environment" src="https://github.com/user-attachments/assets/c2e2a995-672b-4255-8954-872845ac880a" />

## iverilog Simulation Flow
<img width="1183" height="464" alt="iverilog Flow" src="https://github.com/user-attachments/assets/0a8abbec-b04b-470f-b02f-37f5f9092f80" />

## SKY130 RTL Simulation
**Lab1**
GITCLONE the following link
https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop

Libraries are avaible in the following GITHUB
**+ Libraries:** https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop

**Lab2**
Verilog Files are available in the following github link
https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop/tree/main/verilog_files
```
iverilog -o MUX.v tb_MUX.v
./a.out
```
It will generate the VCD file in the folder. Click the file GTK wave window will open and drag and drop the signal you may see the output

**Lab 3**
**MUX Verilog HDL**
```
module good_mux (input i0 , input i1 , input sel , output reg y);
always @ (*)
begin
	if(sel)
		y <= i1;
	else 
		y <= i0;
end
endmodule
```
**MUX Testbench**
```
`timescale 1ns / 1ps
module tb_good_mux;
	// Inputs
	reg i0,i1,sel;
	// Outputs
	wire y;

        // Instantiate the Unit Under Test (UUT)
	good_mux uut (
		.sel(sel),
		.i0(i0),
		.i1(i1),
		.y(y)
	);

	initial begin
	$dumpfile("tb_good_mux.vcd");
	$dumpvars(0,tb_good_mux);
	// Initialize Inputs
	sel = 0;
	i0 = 0;
	i1 = 0;
	#300 $finish;
	end

always #75 sel = ~sel;
always #10 i0 = ~i0;
always #55 i1 = ~i1;
endmodule
```
## Synthesizer
**Yosys**
+ Tool used to COnver RTL to Netlist
+ Yosys is a Synthesizer
<img width="1142" height="286" alt="Yosys" src="https://github.com/user-attachments/assets/40bc515d-2a0d-41fb-a5b3-fa7f8b744f46" />
**Verify the Synthesis**
<img width="1168" height="480" alt="Verify the Synthesis" src="https://github.com/user-attachments/assets/0dda1818-fd5c-41e8-bf52-1b55570c05f1" />
**Logic Synthesis**
  + RTL is the behavioural representation of the Specifications
  + Synthesis is the process of converting RTL code to Gates and the connections are created between the gates namely netlist
  + .lib is the collection of logic modules, Logic gates, different flavours of logic gates (Slow, medium,fast)
<img width="382" height="478" alt="lib" src="https://github.com/user-attachments/assets/0b27462b-280c-47dc-adf4-d0227baa7206" />
+ Faster Cell vs Slower Cell
+ Setup Time & Hold Time
**Synthesis Illustration**
  <img width="910" height="564" alt="Synthesis Illustration" src="https://github.com/user-attachments/assets/a4e1076d-11f5-405a-89b6-9a5716f55589" />

