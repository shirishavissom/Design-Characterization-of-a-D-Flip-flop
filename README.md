# Design-Characterization-of-a-D-Flip-flop
In our design process, we take on the task of designing the fundamental sequential element, namely the Flip-Flop (FF). We create a custom Flip-Flop and conduct a thorough characterization to determine its delay, input capacitance, as well as its setup and hold time.


The construction of a Flip-Flop involves utilizing a pair of latches arranged in a back-to-back configuration. These latches operate on opposite edges of the clock signal and are known as the Master and Slave latches. The Master latch receives the input during one edge of the clock (either negative or positive), while the Slave latch transfers the output of the Master latch to the output during the opposite phase (either positive or negative) of the clock.

Schematic of the flipflop
![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/7eb2db4e-d60e-4ad0-9073-c2ae59de1647)

Symbol of the flipflop:
![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/8d57c92c-5530-4fdd-855f-2903ad1d8e98)

Layout of the flipflop"
![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/34becc77-ef48-4839-9744-c0b53b6648ee)

Extracted View of the flipflop:
![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/57691843-5d7d-4f58-b54b-b217eeb2aa20)

DRC AND LVS CHECKS:
![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/42a9d1b3-f59b-4aa6-8495-46db2f5a5099)

Testbench:
![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/ccfa7b08-36ef-4aac-ad99-7234b38795b1)

In my design process, I begin by simulating the transistor-level schematic using analog simulation. This initial step allows me to verify the functionality of the schematic before proceeding to the layout design. As I progress with the layout implementation, I make it a priority to regularly check for Design Rule Check (DRC) errors, ensuring adherence to the required design rules. Additionally, I perform DRC and Layout vs. Schematic (LVS) checks to ensure proper alignment between the layout and the schematic.

Once the layout is completed, I conduct post-layout simulations on the design. To validate the Flip-Flop's functionality, I provide a rising D input along with a clock signal (including its complement). By observing the corresponding rising Q output, I verify the expected behavior of the design. I also test the Flip-Flop with a falling D input to ensure its proper operation under different conditions. These measures guarantee that the design is functioning correctly and meets the desired specifications.
Characterization:

CELL DELAY TABLE: In my analysis, I construct a Cell Delay Table to examine the behavior of the Flip-Flop (FF) under varying output loads. I systematically vary the load at the FF output, ranging from 1fF to 100fF. The goal is to determine the rising and falling delays of the FF for each load condition.

To accurately measure the delay, I focus specifically on the clock-to-Q delay of the circuit. This is crucial because the FF latches new values only at the active edge of the clock signal. By considering the clock-to-Q delay, I can capture the time it takes for the FF to propagate the input change to the output.

Moreover, I carefully size the transistors in the design to ensure that the rising and falling delays, particularly when the output load is 100fF, exhibit a difference of no more than 10%. This ensures a balanced and symmetric performance of the FF across different load conditions.

![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/0b45c1c8-b5a3-41c8-85d7-ad056c4613f0)

![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/b26c2804-9e8b-4801-a1cc-6616dbb3a1a8)

SINK CAP:
To calculate the input sink capacitance, it is necessary to obtain the current waveform that depicts the current flowing into the input D. Since the sinusoidal voltage source, vsin, is connected to the input D in the schematic, we examine the current originating from vsin. By running the simulation, you will observe a waveform that represents the current into the input D as a function of frequency.

The next step involves calculating the input sink capacitance. To do so, select 10 data points from the waveform and record the corresponding frequency and current for each point. Then, for each data point, calculate the capacitance using the formula C = I / (2 * pi * f), where I represents the current and f represents the frequency. Finally, compute the mean value of the capacitance obtained from the 10 data points.
![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/45eb2adf-5f73-42ac-a033-f2a5af13cc91)
![image](https://github.com/shirishavissom/Design-Characterization-of-a-D-Flip-flop/assets/112213946/137df04d-f554-4ecd-9357-b16566d46657)







