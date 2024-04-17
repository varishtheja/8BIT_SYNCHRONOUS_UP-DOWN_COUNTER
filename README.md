# Aim:
To stimulate and synthesis 4bit Ripple counter using Vivado.

# Software Required:
vivado 2023.2 software.

# Procedure:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

# Program:
module ripple_carry_counter(q, clk, reset);

output [3:0] q;

input clk, reset;

T_FF tff0(q[0], clk, reset);

T_FF tff1(q[1], q[0], reset);

T_FF tff2(q[2], q[1], reset);

T_FF tff3(q[3], q[2], reset);

endmodule

module T_FF(q, clk, reset);

output q;

input clk, reset;

wire d;

D_FF dff0(q, d, clk, reset);

not n1(d, q);

endmodule

module D_FF(q, d, clk, reset);

output q;

input d, clk, reset;

reg q;

always @(posedge reset or negedge clk)

if (reset)

q = 1'b0;

else

q = d;

endmodule

# Output:
![323156666-e2c893bd-0783-455b-a2b7-73c880577315](https://github.com/varishtheja/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/166599469/b3095bb9-ae13-416a-87cc-3375236f9434)


# Result:
Thus the verilog program for 4bit Ripple Counter has been simulated and verified successfully.

About
No description, website, or topics provided.
Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 0 watching
Forks
 0 forks
Report repository
Releases
No releases published
Packages
No packages published
Languages
Verilog
40.2%
 
C
35.5%
 
Batchfile
18.7%
 
Tcl
2.9%
 
Pascal
2.7%
Footer
© 2024 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact
Manage cookies
Do not share my personal information
