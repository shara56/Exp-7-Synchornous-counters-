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

STEP 1

1.Create a new project in Quartus|| Software.

STEP 2

2.Name the project as upc and downc for up and down counter.

STEP 3

3.Create a new verilog hdl file in the project file.

STEP 4

4.Within that file write the program for up and down counter

STEP 5

5.After that run the program and give the clock pulse value as 50 in timing diagram and run the program.




### PROGRAM 

Program for flipflops  and verify its truth table in quartus using Verilog programming.

Developed by: SHARANGINI T K

RegisterNumber: 212222230143

# UPCOUNTER:
```
module upc(clk,A);
input clk;
output reg[0:3]A;
always@(posedge clk)
begin
		A[0]=((((A[1])&(A[2]))&A[3])^A[0]);
		A[1]=(((A[2])&(A[3]))^A[1]);
		A[2]=((A[3])^A[2]);
		A[3]=1^A[3];
end
endmodule
```
# DOWNCOUNTER
```
module downc(clk,A);
input clk;
output reg[0:3]A;
always@(posedge clk)
begin
	A[0]=((((~A[1])&(~A[2]))&A[3])^A[0]);
	A[1]=(((A[2])&(A[3]))^A[1]);
	A[2]=((A[3])^A[2]);
	A[3]=1^A[3];
end
endmodule
```
# RTL LOGIC UP COUNTER AND DOWN COUNTER  

## UPCOUNTER
![image](https://github.com/shara56/Exp-7-Synchornous-counters-/assets/113497104/594de329-4680-49b5-9708-10f204210778)

## DOWNCOUNER
![image](https://github.com/shara56/Exp-7-Synchornous-counters-/assets/113497104/519f546d-ab37-4c95-895d-ad8eee9dafde)

# TIMING DIGRAMS FOR COUNTER  

## UPCOUNTER
![image](https://github.com/shara56/Exp-7-Synchornous-counters-/assets/113497104/6cb8cfee-6a66-4193-bf00-45c721b61072)

## DOWNCOUNTER
![image](https://github.com/shara56/Exp-7-Synchornous-counters-/assets/113497104/74abdc54-873c-4b68-934a-341e1369ef71)

# TRUTH TABLE 

## UP COUNTER:
![image](https://github.com/shara56/Exp-7-Synchornous-counters-/assets/113497104/eb2a4a3b-44f0-4abf-b828-ed46cfa8412d)

## DOWN COUNTER:
![image](https://github.com/shara56/Exp-7-Synchornous-counters-/assets/113497104/544d6443-f690-4ab1-b579-b641f759d385)

# RESULTS 

Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
