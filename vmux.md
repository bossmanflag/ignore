# MUX

    module mux( I,S,Y);
    input [2:0]S;
    input [7:0]I;
    output reg Y;
    
    always@(I,S)
    begin
    case (S)
    3'b000: Y=I[0];
    3'b001: Y=I[1];
    3'b010: Y=I[2];
    3'b011: Y=I[3];
    3'b100: Y=I[4];
    3'b101: Y=I[5];
    3'b110: Y=I[6];
    3'b111: Y=I[7];
    default: Y="z";
    endcase
    end 
    endmodule

Test bench:

    module mux_test;
    
    	// Inputs
    	reg [7:0] I;
    	reg [2:0] S;
    
    	// Outputs
    	wire Y;
    
    	// Instantiate the Unit Under Test (UUT)
    	mux uut (
    		.I(I), 
    		.S(S), 
    		.Y(Y)
    	);
    
    	initial begin
    		// Initialize Inputs
    		I= 8'b01101101;
    		S= 3'b000;
    	end
    	always #10 S[0] = ~S[0];	
    	always #20 S[1] = ~S[1];	
    	always #40 S[2] = ~S[2];
    
    
          
    endmodule

