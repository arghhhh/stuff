
# Papers and Conference Appearances

## Composable iterator processors applied to digital signal processing
### [CAJUN November 20, 2024](https://github.com/arghhhh/julia-signals-systems/blob/main/doc/Julia%20CAJUN%20talk%2020%20Nov%202024.pdf)

This was an updated version of the ORConf 2024 presentation, but aimed for a very different audience.  CAJUN is the Cambridge (MA,USA) Julia users meetup group and so this talk focused more on the Julia language aspects compared with hardware aspects.

## Digital Signal Processing: Modeling with Julia  
### [ORConf 2024](https://fossi-foundation.org/orconf/2024#digital-signal-processing-modeling-with-julia)

This shows how to describe stateful signal processing functions (filters etc) in a way such that they can be composed (combined with other signal processing blocks), without specifying a particular input to be processed.  This allows the system description to be built up separately from any analysis of the overall system, and enables a lot of reuse.  The framework is about six lines of code...

## RISC-V without a Register File 
### [ORConf 2019](https://github.com/arghhhh/minrv32)

Lightning talk on making a RISCV processor which keeps the register file state (31x32bits) in the main memory - so it takes a few cycles to excute each instruction.  Registers could be cached to eliminate back to back writes followed by reads of the same data, and context switching could be made very quick by pointing to alternate regions in memory instead of saving and restoring register contents.  The main motivation for this work was to write a RISCV processor and to use formal verification.

This used [riscv-formal](https://github.com/YosysHQ/riscv-formal) It was simulated and formally verified using open source tools.

## Bounded Integers With Type-Level Constants
### [JuliaCon 2016](https://github.com/arghhhh/bint-juliacon2016)

This is obsolete now - though the way I handled arbitrary length integers as a tuple of fixed length integers is still valid.
A simpler version is at [julia-bints](https://github.com/arghhhh/julia-bints).

## Design and Evaluation of an Audio DAC With non-Uniformly Weighed Dynamic Element Matching 
### [AES Silicon for Audio conference](https://aes2.org/publications/elibrary-page/?id=10149)

This paper promotes using a DC input level sweep to determine whether noise-modulation or tones are present in the output of sigma-delta modulators.  You can see that DC offsets have been applied to some designs to push the small signal region away from tonal regions.

## A chip-set for TETRA digital mobile radio 
### [ESSCIRC](https://ieeexplore.ieee.org/document/1471036)

Baseband signal processing and conversion for public mobile radio - emergency services.  Because there is no overall controlling network assigning channels and controlling transmit levels, this system needs to have very good adjacent channel performance in not transmitting out-of-band and not being susceptible to large adjacent band energy. The DAC used a mixed signal FIR filter and can be considered an early form of dynamic element matching. 


## Robust CMOS compander 
### [ESSCIRC](https://ieeexplore.ieee.org/document/1470874)
Presented in "Proceedings of the 23rd European Solid-State Circuits Conference"

## Robust CMOS compander 
### [JSSC](https://ieeexplore.ieee.org/document/701259)

This is an expanded version of the conference paper in the red IEEE journal.

There are some nasty looking quantization effects - in both the simulated and measured results, which at least indicates that the simulations were accurate.

## The application of redundant number systems to digital sigma-delta modulators 
### [ISCAS](https://ieeexplore.ieee.org/document/409007)

This exploits the fact that significant noise or error can be introduced in front of the quantizer of a sigma-delta modulator - so that only a few MSBs are required to make the decisions.  It is not paricularly useful - there are few applications where you need to run a sigma-delta modulator at such a high rate.  However carry-save arithmetic is a redundant number system, and can be very applicable in implementing decimation filters with very short critical paths.

## Design of high order audio sigma-delta modulators with minimum weighted noise 
### [ISCAS](https://ieeexplore.ieee.org/document/393687)

You can design the noise transfer function (NTF) of high order sigma delta modulators to be minimally audible according to threshold of hearing at each frequency.  Not very useful in practice.  Also, in general, you often want a fairly flat signal transfer function - to avoid overshoot in step inputs (which can potentially cause instability) and to minimize the signal content in the state variables (which results in having to scale the coefficients such that circuit noise becomes more significant).



