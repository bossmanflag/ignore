#  JK

    
    module JK(q,qd,j,k,clk);
    input j,k,clk;
    output reg q = 0,qd=1;
    always@(posedge clk)
    begin
    case({j,k})
    2'b 00 : q = q;
    2'b 01 : q = 0;
    2'b 10 : q = 1;
    2'b 11 : q = ~q;
    endcase
    qd =~q; 
    end
    endmodule


## Testbench


    module JK_test;
    
    	// Inputs
    	reg j;
    	reg k;
    	reg clk;
    
    	// Outputs
    	wire q;
    	wire qd;
    
    	// Instantiate the Unit Under Test (UUT)
    	JK uut (
    		.q(q), 
    		.qd(qd), 
    		.j(j), 
    		.k(k), 
    		.clk(clk)
    	);
    
    	initial begin
    		// Initialize Inputs
    		j = 0;
    		k = 0;
    	clk=0;
    		// Wait 100 ns for global reset to finish
    		#100;
    		j=0;
    		k=1;
    		#100;
    		j=1;
    		k=0;
    		#100;
    		j=1;
    		k=1;
    		
            
    		// Add stimulus here
    
    	end
          always #5 clk = ~clk;
    endmodule
