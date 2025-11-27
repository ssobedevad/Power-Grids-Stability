# Power Grids Stability
[This is work from a university project and therefore I cannot share any code publicly but I can summarise my findings and use graphs.]

This is a third year mathematics group project in which we were tasked with simulating the effect of cascading faliures on a power grid network structure.
I took charge of the coding which involved creating simulations for the network to allow us to calculate the power flow through each node in the network.
I used python to simulate the swing equation with scipy odeint to solve the multlidimensional simultaneous equations at each small timestep.

<img width="640" height="480" alt="MatrixModel_results" src="https://github.com/user-attachments/assets/69ac61d5-c4a6-4ec4-8368-366c85977cb0" />

The initial results are as follows with the nodes being out of sync to begin with and then synchronising over time.
The value o of synchronisation varied based on whether the node was a generator,consumer or neither of power for the grid.

<img width="640" height="480" alt="Kc" src="https://github.com/user-attachments/assets/4c403eea-f800-4bac-9b7b-a83e4f457b14" />

This is a ternary graph that shows the critical value of Kappa (damping on the nodes) for any balance of the three node types. 
Higher Kc leads to a less stable network. 
This shows that a network with a similar number of consumers and generators are stable and the number of passive nodes in the network does not increase stability.

<img width="640" height="480" alt="Cascades" src="https://github.com/user-attachments/assets/d843ca34-08f8-407f-9018-430b1a90dcd1" />

We then simulated a cascade by removing the network edge with the highest power flow through it and then modelled the network as the remaining system was left to deal with the surge.
This stopped when the grid became stable again either as a whole or in many smaller sub grids.
The value alpha_c on the x axis represents the capacity of an edge in the network as a proportion of the initial breaking capacity. 
Overloads are when an edge exceeeds this capacity and a desync occurs when a node is out of phase with the system.
The value of Kc when the entire network survives is at around 1.5.
