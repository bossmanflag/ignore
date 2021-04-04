# johnson

    module jonshon(clk,mode,q);
    input clk;
    input mode;
    output reg [3:0]q =4'b 0000;
    always@(posedge clk)
    begin
    
    if(mode) 
    	q= 4'b 0001;
    
    else
    	q[3]<=~q[0];
    
    	q[2]<=q[3];
    
    	q[1]<=q[2];
    
    	q[0]<=q[1];
    
    end 
    endmodule

## Test bench


    module ringc_test;
    
    	// Inputs
    	reg clk;
    	reg mode;
    
    	// Outputs
    	wire [3:0] q;
    
    	// Instantiate the Unit Under Test (UUT)
    	ringc uut (
    		.clk(clk), 
    		.mode(mode), 
    		.q(q)
    	);
    
    	initial begin
    		// Initialize Inputs
    		clk = 0;
    		mode = 0;
    	
    		// Wait 100 ns for global reset to finish
    		#100;
    		mode=1;
            
    		// Add stimulus here
    
    	end
    	always #5 clk=~clk;
          
    endmodule




