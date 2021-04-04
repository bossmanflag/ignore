# Adder

    module adder(a,b,s,c);
    input[3:0] a ;
    input [3:0] b ;
    input c;
    output reg [4:0]s;
    always @(a,b,c)
    begin
    if(c)
    s = a-b;
    else
    s = a+b;
    end
    endmodule


### Test bench
    module adder_test;
    
    	// Inputs
    	reg [3:0] a;
    	reg [3:0] b;
    	reg c;
    
    	// Outputs
    	wire [4:0] s;
    
    	// Instantiate the Unit Under Test (UUT)
    	adder uut (
    		.a(a), 
    		.b(b), 
    		.s(s), 
    		.c(c)
    	);
    
    	initial begin
    		// Initialize Inputs
    		a = 0;
    		b = 0;
    		c = 0;
    
    		// Wait 100 ns for global reset to finish
    		#100;
    		
    		c=0;
    		a=4'b0000;
    		b= 4'b0001;
    		
    		#100;
    		c=1;
    		a= 4'b1010;
    		b= 4'b0001;
    		
            
    		// Add stimulus here
    
    	end
          
    endmodule
