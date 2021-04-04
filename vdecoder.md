# Decoder


    module Decoder2x4(a,b,y0,y1,y2,y3);
    input a,b;
    output y0,y1,y2,y3;
    assign
    y0=(~a&~b),
    y1=(~a&b),
    y2=(a&~b),
    y3=(a&b);
    
    endmodule


## Test bench

    module dec2x4_test;
    
    	// Inputs
    	reg a;
    	reg b;
    
    	// Outputs
    	wire y0;
    	wire y1;
    	wire y2;
    	wire y3;
    
    	// Instantiate the Unit Under Test (UUT)
    	Decoder2x4 uut (
    		.a(a), 
    		.b(b), 
    		.y0(y0), 
    		.y1(y1), 
    		.y2(y2), 
    		.y3(y3)
    	);
    
    	initial begin
    		// Initialize Inputs
    		a = 1;
    		b = 0;
    
    		// Wait 100 ns for global reset to finish
    		#100;
    		a=0;
    		b=1;
    		
    		#100;
    		a=1;
    		b=1;
            
    		// Add stimulus here
    
    	end
          
    endmodule


