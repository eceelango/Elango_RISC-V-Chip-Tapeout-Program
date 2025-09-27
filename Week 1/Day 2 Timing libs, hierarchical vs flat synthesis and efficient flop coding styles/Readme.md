# Timing libs, hierarchical vs flat synthesis and efficient flop coding styles
## Library
**.lib**
+ PVT Variation due to fabrication
   - Process
   - Voltage
   - Temperature
## Types of Gates : Std Cell
<img width="1050" height="398" alt="Flavours of Gates" src="https://github.com/user-attachments/assets/85eddaf8-2247-4911-98b5-27776d93e566" />

**Lab1**
```
module dff_async_set ( input clk ,  input async_set , input d , output reg q );
always @ (posedge clk , posedge async_set)
begin
	if(async_set)
		q <= 1'b1;
	else	
		q <= d;
end
endmodule
```
