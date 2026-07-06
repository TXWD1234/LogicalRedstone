# Adder - LogicalRedstone Project Demo

This demo consist of the implementation of a **half adder** and a **full adder** made with the *LogicalRedstone* components.
The half adder calculates the result from the addition of 2 one bit number (0 ~ 1).
The full adder calculates the result from the addition of 2 8-bit number (0 ~ 255).

## Half Adder
The half adder have 2 input pins and 2 output pins:
- input: first adder number
- input: second adder number
- output: result (the value for the original digit)
  - this is a XOR gate
- output: carry (the additional result for the next digit)
  - this is an AND gate

**Circuit Picture:**
![picture](https://github.com/TXWD1234/LogicalRedstone/docs/readme-assets/demo-circuit/half-adder.png)

**Block Diagram:**
![picture](https://github.com/TXWD1234/LogicalRedstone/docs/readme-assets/demo-circuit/symbols.png)

## Full Adder
The full adder combines and chains half adders to calculate bigger values.
There are 16 input pins and 8 output pins in this design for 2 8-bit integer input and 1 8-bit integer output. *Theoretically, there could be much more IO pins just by stacking more half adders, but that would result the circuit become very slow to finish the calculation.*

For each digit, there is one half adder calculating the result of the input of that digit.
In addition, for every digit after the first digit (the most insignificant digit), there's another half adder calculating the sum of the `RESULT` of the current digit, and the `CARRY` of the previous digit.
The `CARRY` of every digit after the first digit is calculated by combining the `CARRY` of the 2 half adder in that digit. Since at most only one of them is possible to have `CARRY`, another half adder is not required.

**Circuit Picture:**
![picture](https://github.com/TXWD1234/LogicalRedstone/docs/readme-assets/demo-circuit/full-adder.png)