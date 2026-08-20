# Seven-Segment-Display-Driver-using-Verilog-HDL
# EXP NO: 2.A Seven-Segment Display Driver using Verilog HDL
# Aim
To design and simulate a seven-segment display driver using Verilog HDL, and verify its functionality through a testbench in the Vivado 2023.1 environment. The objective is to implement the logic that converts a 4-bit binary input into the corresponding 7-segment display output for the digits 0 to 9.

# Apparatus Required
Vivado 2023.

# Procedure

1. Launch Vivado 2023.1
Open Vivado and create a new project.
2. Design the Verilog Code
Write the Verilog code for the seven-segment display, defining the logic that maps a 4-bit binary input to the corresponding segments (a to g) of the display.
3. Create the Testbench
Write a testbench to simulate the seven-segment display behavior. The testbench should apply various 4-bit input values and monitor the corresponding output on the seven-segment display.
4. Create the Verilog Files
Create both the design module and the testbench in the Vivado project.
5. Run Simulation
Run the behavioral simulation to verify the output. Ensure the seven-segment display behaves correctly for binary inputs 0000 to 1001 (decimal 0 to 9).
6. Observe the Waveforms
Analyze the output waveforms in the simulation window, and verify that the correct segments light up for each digit.
7. Save and Document Results
Capture screenshots of the waveform and save the simulation logs. These will be included in the lab report.

# Verilog Code for Seven-Segment Display
```
// seven_segment_display.v
'timescale ins/1ps
module seven_segment_display (
    input  wire [3:0] num,     
    output reg  [6:0] seg      
);
always @(*) 
begin
    case(num)
        4'd0: seg = 7'b1111110;
        4'd1: seg = 7'b0110000;
        4'd2: seg = 7'b1101101;
        4'd3: seg = 7'b1111001;
        4'd4: seg = 7'b0110011;
        4'd5: seg = 7'b1011011;
        4'd6: seg = 7'b1011111;
        4'd7: seg = 7'b1110000;
        4'd8: seg = 7'b1111111;
        4'd9: seg = 7'b1111011;
        default: seg = 7'b0000000;
    endcase
end
endmodule
```
# Testbench for Seven-Segment Display
```

`timescale 1ns / 1ps
module tb_seven_segment_display;
reg  [3:0] num;
wire [6:0] seg;
seven_segment_display uut (
    .num(num),
    .seg(seg)
);

initial 
begin
    num = 4'd0;
    #10 num = 4'd0;
    #10 num = 4'd1;
    #10 num = 4'd2;
    #10 num = 4'd3;
    #10 num = 4'd4;
    #10 num = 4'd5;
    #10 num = 4'd6;
    #10 num = 4'd7;
    #10 num = 4'd8;
    #10 num = 4'd9;
    #10 $stop;
end
endmodule
```

# Simulated Output

<img width="826" height="561" alt="image" src="https://github.com/user-attachments/assets/5800ad86-0377-4b64-9b7b-69177ac27a37" />


# Conclusion
In this experiment, a seven-segment display driver was successfully designed and simulated using Verilog HDL. The simulation results confirmed that the display correctly represented the digits 0 to 9 based on the 4-bit binary input. The testbench effectively verified the functionality of the seven-segment display by applying various input combinations and observing the corresponding segment outputs.

This experiment highlights how Verilog HDL can be used to control hardware components like a seven-segment display in digital systems.
