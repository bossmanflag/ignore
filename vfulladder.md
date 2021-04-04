# Full Adder

    module fulladder(a,b,c,s,cr);
    input a,b,c;
    output reg s,cr;
    always @(a,b,c)
    begin
     s= a^b^c;
     cr = (a&b)|(b&c)|(c&a);
    end
    endmodule



## Test bench

    module fulladder_test;
    
    	// Inputs
    	reg a;
    	reg b;
    	reg c;
    
    	// Outputs
    	wire s;
    	wire cr;
    
    	// Instantiate the Unit Under Test (UUT)
    	fulladder uut (
    		.a(a), 
    		.b(b), 
    		.c(c), 
    		.s(s), 
    		.cr(cr)
    	);
    
    	initial begin
    		// Initialize Inputs
    		a = 0;
    		b = 0;
    		c = 0;
    
    		// Wait 100 ns for global reset to finish
    		#100;
    		a=1'b0;
    		b=1'b1;
    		c=1'b0;
            
    		// Add stimulus here
    
    	end
          
    endmodule


