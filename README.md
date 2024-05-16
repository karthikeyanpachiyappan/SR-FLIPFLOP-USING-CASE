
## <p align='center'><b>SR-FLIPFLOP-USING-CASE</b>

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/karthikeyanpachiyappan/SR-FLIPFLOP-USING-CASE/assets/155143878/003dcd8c-0883-460e-9218-c42687c3edae)


 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/karthikeyanpachiyappan/SR-FLIPFLOP-USING-CASE/assets/155143878/699ec245-0218-4203-bed7-e52d10eb64d1)


 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/karthikeyanpachiyappan/SR-FLIPFLOP-USING-CASE/assets/155143878/c7019571-212b-47f8-af3f-c1fe166a451f)


 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/karthikeyanpachiyappan/SR-FLIPFLOP-USING-CASE/assets/155143878/da3f2c3e-5a64-4e73-a89d-41a50875c2e7)


 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

```
Step 1: Open Quartus II in your laptop.
Step 2: Write code to implement SR flipflop using verilog and validating their functionality using their functional tables.
Step 3: Run compilation to check for errors.
Step 4: Open waveform output and load input values.
Step 5: Run simulation to get the output.
Step 6: Open in RTL viewers to get RTL diagram output.
```

**PROGRAM**


## Developed by:KARTHIKEYAN P
## RegisterNumber:212223230102
```
module sr_flipflop(q, q_bar, s, r, clk, reset);
  input s, r, clk, reset;
  output reg q;
  output q_bar;

  always @(posedge clk) begin
    if (!reset) 
      q <= 1'b0;
    else begin
      case ({s, r})
        2'b01: q <= 1'b0;
        2'b10: q <= 1'b1;
        2'b11: q <= 1'bx;
        default: q <= q;
      endcase
    end
  end

  assign q_bar = ~q;
endmodule
```


**RTL LOGIC FOR FLIPFLOPS**

![image](https://github.com/karthikeyanpachiyappan/SR-FLIPFLOP-USING-CASE/assets/155143878/ca1706c1-a08e-4d73-a357-d714a32cf8af)


**TIMING DIGRAMS FOR FLIP FLOPS**

![image](https://github.com/karthikeyanpachiyappan/SR-FLIPFLOP-USING-CASE/assets/155143878/8552e55c-c9e3-471c-95f5-1edfface4177)


**RESULTS**

Thus the program to implement a SR flipflop using verilog and validating their functionality using their functional tables is successfully completed.
