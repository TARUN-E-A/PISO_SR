# PISO_SR

# AIM: 

To simulate and synthesis  PISO_SR using vivado. 

# APPARATUS REQUIRED: 
vivado 2023.2 software. 

# PROCEDURE: 

STEP:1 Start the vivado software, Select and Name the New project. 
STEP:2 Select the device family, device, package and speed. 
STEP:3 Select new source in the New Project and select Verilog Module as the 
Source type. 
STEP:4 Type the File Name and module name and Click Next and then finish 
button. Type the code and save it. 
STEP:5 Select the run simulation and then run Behavioral Simulation in the 
Source Window and click the check syntax. 
STEP:6 Click the simulation to simulate the program and give the inputs and 
verify the outputs as per the truth table. 
STEP:7 compare the output 
# truth table.
![image](https://github.com/RESMIRNAIR/PISO_SR/assets/154305926/f0f2d979-b298-4693-b5c8-8eea850936d4)
# verilog code:
```
module piso_shift_register(
  input wire clk,       // Clock input
  input wire reset,     // Reset input
  input wire parallel_in,  // Parallel input
  output reg serial_out  // Serial output
);

// Initialize shift register
reg [7:0] shift_reg = 8'b00000000;

always @(posedge clk or posedge reset) begin
  if (reset) begin
    // Reset shift register
    shift_reg <= 8'b00000000;
    serial_out <= 1'b0;
  end
  else begin
    // Shift data in
    if (parallel_in) begin
      shift_reg <= {shift_reg[6:0], parallel_in}; // Shift in parallel data
    end
    
    // Serial output
    serial_out <= shift_reg[7];
  end
end

endmodule
```
# output
![image](https://github.com/TARUN-E-A/PISO_SR/assets/163630871/afef8a44-1faa-4bdb-b193-fb677c6f450e)

# result
thus PISO_SR is succesfully completed using vivado
