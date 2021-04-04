# Sync up    
    module syncup(
        clk,rst,count);
    input clk, rst;
    output reg [3:0] count = 0;
    always @(posedge clk)
    begin
    if(rst)
    count = 0;
    else
    count = count+1;
    end
    
    endmodule

## Testbench


    module synctest;

	// Inputs
	reg clk;
	reg rst;

	// Outputs
	wire [3:0] count;

	// Instantiate the Unit Under Test (UUT)
	syncup uut (
		.clk(clk), 
		.rst(rst), 
		.count(count)
	);

	initial begin
		// Initialize Inputs
		clk = 0;
		rst = 0;

		// Wait 100 ns for global reset to finish
		
		#100 rst=1;		#150 rst=0;

		
		
		
        
		// Add stimulus here

	end
	
	always #5 clk = ~clk;
    endmodule


