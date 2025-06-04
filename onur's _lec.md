# Onur's Lectures (1-6)

## Lecture 1

- we need computer to solve problems(computational) and computer solve problems by orchestrating electrons
- Here is the transformation hierarchy:

    - Problem
    - Algorithm
    - Program
    - System Software
    - SW/HW Interface
    - Micro Architecture
    - Logic
    - Devices
    - Electrons
- Smallest level (electron level) , before that come devices (here comes up `transistors`)
- One level up the transistor comes up logic comprising `AND,OR,NOT,NAND etc`


## Lecture 2
-   `By reducing the size of transistors we can add more components on unit area`(size of transistor can be reduced by using material with better properties, creating new devices technology) this is known as `MOORE'S LAW`
- Transistor in series are slower than in parallel.
- Dynamic power is consumed by transistors only when signals change but static power is consumed even when signals are not changing
- We can acheive duality in Boolean expression by

   - Swapping AND and OR gates
   - Swapping constant 1 and constant 0
- In `SOP` F eqauls OR of all input variable combination result in 1
- In `POS` F eqauls AND  of all input variable combination result in 0
- `Programmable Logical Array (PLA)` is a combinational block ; it is an array of AND gates follwed by OR gates 
- Any logical circuit could be implemented with PLA


## Lecture 3
- {AND,OR,NOt} are logically complete meaning only these three combined can make logic for any problem
- `TRI-STATE BUFFER` enables gating different signals onto a wire. If enable signals is zero output will be a `floating signal` (signal that is not driven by any circuit or high impedance)
- `Memory` is comprised of locations that can write to read from.
- The number of bits of information stored in each location is called `Addressibility`
- The entire set of unique locations in memory is referred as `address space`
- In `Asynchronous machine` state transition occur when they occur and there is nothing that synchronizes when each state transition must occur
- In `Synchronous machine` state transitions take place after fixed unit of time
- why we need flipflop?
  
  we need flipflop because there is a problem with latches.

  what problem?

  we cannot wire a clock to `write enable` of latch (latch is transparent). Latch only popagates D to Q when clock is high.

  ## Lecture 4

- `FPGA` stands from `Field Programmable Gate Array`, it is a software reconfigurable hardware substrate. It composed of many switches and LUTs
 - Finite State Machine: State Encoding
     - Fully Encoded (e.g., use log(num_states) bits to represent states)
     - 1 Hot-Encoded (e.g., 1000,0100,0010,00001)
     - Output Encoded (e.g., 001,100,010,110)

## Lecture 5

- We can do concatenation like 
    - `` assign y={a[2],a[1],a[1],a[0]} ``
    - `` assign y= {4{a[0]}}``

- `` assign y=&a `` is same as;
    - `assign y= a[3]&a[2]&a[1]&a[0]`
- `?'` is known as `ternary operator` because it deals with three variables mostly at a time
- Number is expressed as `  N'B xx`
    - N is number od bits
    - B is base (binary,hexa etc)
    - xx are values expressed in base
- Time is defined only in `simulation` and never is synthesis
- In `Non-Blocking Statements` all assignments are made at the end of blocks and are made in parallel
- In `Blocking Statements` assignments are made imediately and wait until first assignment complete

## Lecture 6

- ### Combinational Circuit Timing
    
   - Here `Delay is due to capacitances and resistances
   - Different inputs have different delays
   - Delays change with aging of circuit
   - ` Contamination Delay ` is the delay until output starts changing
   - `  Propagation Delay` is the delay until output finishes change

- ### Sequential Circuit Timing
  
   - `Setup time` is a time before clock edge that input data must be stable
   - `Hold time` is a time after clock edge that data must be stable 
   - 'Aperture time` is a time around clock edge that data must be stable
   - `FlipFlop output timing` 
       - Contamination delay (clk-q)
       - Propagation delay (clk-q)
   - Setup time constraint `Tc > t(pcq) + t(pd) + t (setup) `
   - Hold time constraint ` t(ccq) + t(cd) > t(hold)`
   - `Clock Skew` is the difference between two clock edges, it will effect setup time constraint and hold time constraint as;
       - `Tc > t(pcq) + t(pd) + t (setup) + t(skew)`
       - ` t(ccq) + t(cd) > t(hold) + t(skew)`



