# Four-Way-Traffic-Light-system-
Four Way Traffic Light system  USING D FLIP FLOP, Karnaugh Maps, flip-flop CIRCUIT DIAGRAM in multisim. Project PCB DESIGN.



Four Way Traffic Light system





 
1.	INTRODUCTION 
 Four Way Traffic Light Using D Flip Flop Due to the increase in traffic, the user of vehicles is facing too many problems on roads. Sometimes the roads get block, and the traffic flow is disturbed, and it leads to hazardous accidents in which a lot of people lose their lives. In order to control the flow of traffic, traffic signals are being implemented which helps in the smooth flow of traffic. In big cities, there are 8 lane traffic, and 4 traffic signals people will find at the junction. 
 The designing of 4-way traffic signal using logic gates & flip flops is totally based on the concepts that are covered in Digital Logic Design Course. (coordination, 1967)



1.1 WHAT IS D FLIP FLOP TRUTH TABLE?
 The D Flip Flop is by far the most important of the clocked flip-flops as it ensures that ensures that inputs S and Rare never equal to one at the same time. The D-type flip flop are constructed from a gated SR flip-flop with an inverter added between the S and the R inputs to allow for a single D (Data) input
D flip flop is the most important flip flop from other clocked types. It ensures that at the same time, both the inputs, i.e., S and R, are never equal to 1. The Delay flip-flop is designed using a gated SR flip-flop with an inverter connected between the inputs allowing for a single input D(Data). (Digital Teaching Aid (DED Philippinen, 2019)

2. PROBLEM STATEMENT  
1.To avoid the collision of vehicles by giving an appropriate signal to different directions. 
2.To control the consistency of the cycle of the traffic. 
3. To avoid collision vehicles with public

3.EQUIPMENT’S
	Personal Computer
	Multisim Software
	Proteus 8 software

 

4. IN THIS MINI PROJECT WE WILL DISCUSS ABOUT. 
	Block diagram of this project
	Truth Table 
	Karnaugh Mapping 
	Circuit design 
	PCP design

5. COMPONENTS 
1.	1 3 D flip flop (IC7474)
2.	7 AND GATE(IC7408)
3.	3 OR GATE(IC7432)
4.	1 NOT GATE(IC7404)
5.	BATTERY 9V
6.	4 L.E.D traffic light  
7.	1 DIGITAL CLOCK GENERATOR 
8.	WIRE 







6. BILL OF MATERIAL
 














7. METHODOLOGY

In this project we work through a design example from problem statement to digital circuits. We are going to do a new system of traffic lights based on the usual European model. We have to design a synchronous digital circuit, a Moore Machine, which operates this new type of traffic light at a simple road crossing. 

7.1.1BLOCK DIAGRAM
                                                                                         
N-S    	E-W

RED	GREEN
RED	AMBER
RED	RED
GREEN	RED
AMBER	RED
RED	RED
RED	GREEN






Figure 1:example of state
                                                                                                                    
                                                                                                       









                   Figure: block diagram of this project 

    
There are six lights to operate. The Red, Amber, and green lights in the North-South direction will be designated as R1, A1, G1. Similarly, the lights in the East-West direction will be called R2, A2, and G2. When the digital signals are in the Logic-1 state they turn their respective lights on, otherwise the lights are off. A digital clock signal will be supplied and at each clock pulse the lights should change according to the schedule given above. There are two types of road crossing:

 7.1 MOW MANY STATES DO WE NEED IN OUR PROJECT?
First understanding the problem" refers to the understanding of the verbally described problem and its translation into digital circuit terms. Usually, the determination of the number of required states is not a trivial problem; and the determination of the minimum number of states may be very difficult. Probably, a reasonable approach is to find a number of states for which a state transition diagram can be constructed and then look at the problem again because, possibly, we can discover that some states are duplicated and thus can be eliminated. Our problem is simple enough, so this will not happen here.













Looking at the transition table, we see that there are six states in the first column (dangerous intersection) and four states in the second. However, we do not need ten states because all four states in the second column (the same six outputs) are included in the six states of the first column. So We need only six states. Let us number them 1 to 6 in the order they are shown in the state transition table.




State NO	R1	A1	G1	R2	A2	G2
1	1	0	0	0	0	1
2	1	0	0	0	1	0
3	1	0	0	1	0	0
4	0	1	0	1	0	0
5	0	0	0	1	0	0
6	1	0	0	1	0	0


 
   Figure: - Sequence of traffic light

Two states (3 and 6), labelled A and B, have the same traffic light outputs. Could they be merged as one state? The answer is no, unfortunately, because the state after 3 is 4 while the state after 6 is 1.

7.2 SELECT THE TYPE AND NUMBER OF FLIP-FLOPS FOR THE CIRCUIT. 
Since the number of states is equal to six, the minimum number of flip-flops, which can support six states,. The maximum number of flip-flops one may use is six (one flip-flop per state). For this design example we will use three D-type flip-flops. There will be two unused states. (Lights, 2015)

7.3 ASSIGN STATE NUMBERS TO FLIP-FLOP OUTPUTS AND CONSTRUCT THE TRANSITION TABLE.
We could make R1=Q1 and R2=Q2,  if these simple assignments will give us a correct complete state assignment. The third output, Q3 has to be assigned such that all used states are distinct. One possible set of assignments are shown below:
STATE	Q1	Q2	Q3	R1	A2	G1	R2	A2	G2
1	1	0	0	1	0	0	0	0	1
2	1	0	1	1	0	0	0	1	0
3	1	1	1	1	0	0	1	0	0
4	0	1	1	0	0	1	1	0	0
5	0	1	0	0	1	0	1	0	0
6	1	1	0	1	0	0	1	0	0
7	0	0	0	X	X	X	X	X	X
8	0	0	1	X	X	X	X	X	X

Table: - Output Circuit





7.4 KARNAUGH MAPS MAPPING OF OUTPUT CIRCUITS


Q1	00	01	11	10
0	X	X	0	0
1	1	1	1	1
Q1	00	01	11	10
0	X	X	0	1
1	0	0	0	0







Q1	00	01	11	10
0	X	X	0	0
1	1	1	1	1
Q1	00	01	11	10
0	X	X	1	1
1	0	0	1	1



 



Q1	00	01	11	10
0	X	X	0	0
1	0	1	0	0
Q1	00	01	11	10
0	X	X	0	0
1	1	0	0	0



 


The output circuits are quite a lot simpler and smaller, but of course, we have to redesign the state sequencing.
logic circuitry with the new flip-flop state assignments.

S	State	Q1	Q2	Q3	State(t+1)	D1	D2	D3
0	7	0	0	0	X	X	X	X
0	8	0	0	1	X	X	X	X
0	1	1	0	0	2	1	O	1
0	2	1	0	1	3	1	1	1
0	3	1	1	1	4	0	1	1
0	4	0	1	1	5	1	1	0
0	5	0	1	0	6	1	1	0
0	6	1	1	0	0	1	0	0


S	State	Q1	Q2	Q3	State(t+1)	D1	D2	D3
1	7	0	0	0	X	X	X	X
1	8	0	0	1	X	X	X	X
1	1	1	0	0	2	1	O	1
1	2	1	0	1	4	0	1	1
1	3	1	1	1	X	X	X	X
1	4	0	1	1	5	0	1	0
1	5	0	1	0	1	1	0	0
1	6	1	1	0	X	X	X	X









7.4 KARNAUGH MAPS MAPPING OF STATE SEQUENCING
 
Figure: - k map of state sequencing

In summary we have the following circuits to build:
D1 = S'•Q2' + Q3'
D2 = S'•Q1' + Q3
D3 = Q2' + Q1•Q3
R1 = Q1
A1 = Q1'•Q3'
G1 = Q1'•Q3
R2 = Q2
A2 = Q2'•Q3
G2 = Q2'•Q3'
9.	RESULT AND DISCUSSION 

CIRCUIT DIAGRAM
North and south rode signal are green and east and west rod signal red for 5s. so north and south land vehicle can go for 5 s. 
 
North and south rode signal are yellow and east and west signal red for 5s. so north and south land vehicle can go for 5 s after 5s light will be red so yellow is warning to NS vehicle. 
 

All signals are red this time people can cross the rout. people can go one side to another side.
 
east and west rod signal are green and east and North and south rode signal red for 5s. east and west rode vehicle can go for 5 s. 

 

east and west rod signal are yellow and east and North and south rode signal red for 5s. east and west rode vehicle can go for 5 s. after 5s light will be red so yellow is warning to EW vehicle. 
 

All signals are red this time people can cross the rout. people can go one side to another side.
 





9.1 PCB DESIGN OF THIS PROJECT 
 
3D DIGICAM OF THIS CIRCUIT
 


 


10.CONCLUSION:

In conclusion, the project “FOUR-WAY TRAFFIC LIGHT USING D FLIP FLOP “has been successfully designed and tested. As we know, traffic light is an object that control the movement of the vehicle. It can prevent the traffic jams from happening. We are proud of the success of the projects we have implemented. We are applied what we have learned during the class and develop new skill during this project.




Video link of this project 
https://youtu.be/bfRiodiFAjk
 














11.	REFERENCES
coordination, T. l. (3 23, 1967). 184. Retrieved from wikipedia: https://en.wikipedia.org/wiki/Traffic_light_control_and_coordination#History
Digital Teaching Aid (DED Philippinen, 8. p. (5 4, 2019). nzdl.com. Retrieved from nzdl.: http://www.nzdl.org/cgi-bin/library?e=d-00000-00---off-0cdl--00-0----0-10-0---0---0direct-10---4-------0-1l--11-en-50---20-about---00-0-1-00-0-0-11-1-0utfZz-8-00&cl=CL4.40&d=HASHfb0a7f85db79899f86b6a0.11.1.4&gt=1
Engelmann, F. C. (2 12, 2018). YouTube. Retrieved from Youtuve.
Lights, L. 1.-T. (3 7, 2015). docplaye,.net. Retrieved from docplaye: https://docplayer.net/23224026-Lecture-10-a-design-example-traffic-lights.html



