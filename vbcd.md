# bcd


    module bcd_to_grey(b[3:0], g[3:0]);
    input [3:0] b;
    output [3:0] g;
    
    assign g[3] = b[3];
    assign g[2] = b[3] ^ b[2];
    assign g[1] = b[2] ^ b[1];
    assign g[0] = b[1] ^ b[0];
    endmodule

## Test bench

    module b2g_test;
    
    	// Inputs
    	reg [3:0] b;
    
    	// Outputs
    	wire [3:0] g;
    
    	// Instantiate the Unit Under Test (UUT)
    	bcd_to_grey uut (
    		.b(b), 
    		.g(g)
    	);
    
    	initial begin
    		// Initialize Inputs
    		 b = 4'b 0011;
    
    		// Wait 100 ns for global reset to finish
    		#100;
            
    		// Add stimulus here
    
    	end
          
    endmodule

