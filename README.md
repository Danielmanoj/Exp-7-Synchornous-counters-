# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
1.Set the input as clock.

2.Register the output of 4 bit.

3.Use Posedge on the input clock.

4.For Up counter use AND and OR gates to declare the value of each bit.

5.For Down counter use AND, OR and NOT gates to declare the value of each bit.

6.End the module.





### PROGRAM 
```

Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: MANOJ G
RegisterNumber:  212222240060

```
## Program for Up-counter:
```
module uc(clk,A);
input clk;
output reg [3:0]A;
always@(posedge clk)
begin
A[3]=((A[2]&A[1])&A[0])^A[3];
A[2]=(A[1]&A[0])^A[2];
A[1]=(A[0]^A[1]);
A[0]=1^A[0];
end
endmodule

```


### Program for down counter:
```
module dc(clk,A);
input clk;
output reg [3:0]A;
always @(posedge clk)
begin
A[3]=((~A[2])&(~A[1])&(~A[0]))^A[3];
A[2]=((~A[1])&(~A[0]))^A[2];
A[1]=(~A[0])^A[1];
A[0]=1^A[0];
end
endmodule
```




### RTL LOGIC: 
### UP COUNTER:


![243985988-3f2471b0-7668-4e47-82ff-0feae9a5024d](https://github.com/Danielmanoj/Exp-7-Synchornous-counters-/assets/69635071/a4c6de07-d1cc-4ba2-b80b-efd42308b09e)


### DOWN COUNTER:
![243986090-3e4d85a6-9c5d-4c6f-80ae-38583b5f823c](https://github.com/Danielmanoj/Exp-7-Synchornous-counters-/assets/69635071/b224c115-e7a6-4d5d-9ed2-8a6429588166)


### TIMING DIGRAMS: 

### UP COUNTER:
![243987254-e7ae2e09-026e-4325-8d0e-4ba24d76a377](https://github.com/Danielmanoj/Exp-7-Synchornous-counters-/assets/69635071/62e681c0-168c-44b7-9279-f8fa8c75a2c7)


### DOWN COUNTER:
![243987254-e7ae2e09-026e-4325-8d0e-4ba24d76a377](https://github.com/Danielmanoj/Exp-7-Synchornous-counters-/assets/69635071/d3206755-c5b7-45c7-b20e-f80845d2dd48)








### TRUTH TABLE 

## UP COUNTER
![243988306-66515381-dfea-4f5a-a4cc-8a7ae3f899d8](https://github.com/Danielmanoj/Exp-7-Synchornous-counters-/assets/69635071/fa73e36f-b5e7-451c-8a59-402f5a52b48f)

## DOWN COUNTER
![243988274-e4e4b54b-f2a1-402e-a924-df6ef45f1541](https://github.com/Danielmanoj/Exp-7-Synchornous-counters-/assets/69635071/4513647b-3341-4da0-b44d-7d81e2ad2451)







### RESULTS 


Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
