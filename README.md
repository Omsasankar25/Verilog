# Verilog
# Inverter Design Code
module Ominverter(y,a);
	output y;
	input a;
	
	assign y=~a;
	
endmodule
# Inverter Testbench Code
module Ominvertertb;
  reg a;
  wire y;

  //Design Instance
  Ominverter jinv(y,a);
  
	initial
	begin
		$display ("RESULT\ta\ty");

		a = 1; # 100; // Another value
		if ( y == 0 ) // Test for inversion
			$display ("  PASS  \t%d\t%d",a,y);
		else
			$display ("  FAIL \t%d\t%d",a,y);

		a = 0; # 100; // Initial value is set
		if ( y == 1 ) // Test for inversion
			$display ("  PASS  \t%d\t%d",a,y);
		else
			$display ("  FAIL  \t%d\t%d",a,y);

		a = 1; # 50; // Another value
		if ( y == 0 ) // Test for inversion
			$display ("  PASS  \t%d\t%d",a,y);
		else
			$display ("  FAIL  \t%d\t%d",a,y);

		a = 0; # 100; // Initial value is set
		if ( y == 1 ) // Test for inversion
			$display ("  PASS  \t%d\t%d",a,y);
		else
			$display ("  FAIL  \t%d\t%d",a,y);

	end
  
