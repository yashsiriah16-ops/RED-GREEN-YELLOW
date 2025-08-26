# RED-GREEN-YELLOW
Designed a traffic light controller using the Mealy FSM model in Verilog. Outputs depend on both state and input, enabling faster transitions. Simulated transitions between Red, Green, and Yellow states. Gained insights into input-driven state logic and efficient FSM implementation using Vivado simulation and waveform analysis.
THIS THE TEST BENCH OF RED,GREEN,YELLOW LIGHT CONTROLLER!!!

module rygtb;
    reg clk;
    wire [0:2] light;
    ryg uut (
        .clock(clk),
        .light(light)
    );
    always #5 clk = ~clk;

   initial begin
        clk = 0;
        #100 $finish;
    end
    initial begin
        $dumpfile("cyclic.vcd");
        $dumpvars(0, rygtb);
    end
endmodule
