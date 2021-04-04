#  SR  

    module SR(q,qd,s,r,clk);
    input s,r,clk;
    output reg q=0, qd=1;
    always @(posedge clk)
    begin
    	case({s,r})
    	2'b00: q=q;
    	2'b01: q=1'b 0;
    	2'b10: q=1'b 1;
    	2'b11: q=1'b x;
    	endcase
    	qd=~q;
    end
    endmodule

## Testbench

    module SR_test;

	// Inputs
	reg s;
	reg r;
	reg clk;

	// Outputs
	wire q;	wire qd;


	// Instantiate the Unit Under Test (UUT)
	SR uut (
		.q(q), 
		.qd(qd), 
		.s(s), 
		.r(r), 
		.clk(clk)
	);

	initial begin
		// Initialize Inputs
		s = 0;
		r = 0;
		clk = 0;

		// Wait 100 ns for global reset to finish
		#100;
		s =0;
		r =1;
		#100;
		s=1;
		r=0;
		#100;
		s=1;
		r=1;
	end
	always #5 clk = ~clk;
          
    endmodule
