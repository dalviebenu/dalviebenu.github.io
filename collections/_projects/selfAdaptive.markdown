---
title:  "Self Adaptive Systems Project"
permalink: /projects/selfAdaptive-proj/
layout: page
---
## What is the Self Adaptive Systems Project?
This was the final project for the Self Adapative Systems course at Vrije University done during my masters degree. We were given a simulation of an IoT smart city (called DingNet), where there are nodes spread around the city which send data to gateways which forward the data to application servers. The simulation provides data on the energy used per node, the number of messages sent and lost, among other data (such as the spreading factor of a node). The task was to create a self adaptive system to keep the percentage of packets lost below 5% while optimising energy usage in the nodes. 

To do this we were given access to a managing system called UPISAS (in python) which we used to monitor the status of the IoT simulation and make changes to achieve the stated goal. 

## How does it work?
We created a loop in python which follows the MAPE cycle (Measure, Analyse, Plan and Execute). Upisas will pull data about the IoT simulation (namely energy usage and spreading factor of the nodes and the percentage of packets loss between nodes and gateways). We then used a Proportional-Integral-Derivative (PID) controller to determine how to change the energy level and spreading factor of the nodes to meet the 5% packet loss level. If the packet loss is below 5% then the energy level is decreased (to optimise energy usage).

![no:_adaption](/images/mote1_no_adaption.jpeg)

*Image 1 the packet loss agaisnt time for node 1 without any adaption*

![adaption](/images/mote1_adaption.jpeg)

*Image 2 the packet loss agaisnt time for node 1 with adaption*

From image 1 and 2 we can see that the adaptation strategy was sucessful in reducing the packet loss below 5%.

In a technical level the DingNet simulation was containerised, UPISAS would run this container and containously monitor it and execute commands in the container according to the PID controller algorithm.


## What did I learn?
Key takeaways include learning about different adaption algorithms and how to make systems solve issues with minimal human intervention. 

The UPISAS repository is available [here](https://github.com/dalviebenu/UPISAS_Group_5_1){:target="_blank"}.

The Dingnet repository is available [here](https://github.com/dalviebenu/DingNet_Group_5_1){:target="_blank"}.

To read the report for this project which goes into more detail go [here][1]

[1]:{{ site.url }}/downloads/report.pdf