Contiki - a Lightweight and Flexible Operating System for Tiny Networked Sensors
##############################################################################################

:date: 2019-3-23
:category: Paper Review
:author: Joseph Anthony C. Hermocilla


This paper [DUNKELS2005]_ describes the design and implementation of Contiki. The paper describes the characteristics of sensor 
networks and its special requirements. These special requirements were considered in Contiki's design. For example, 
nodes in sensor networks are tiny and limited in processing power and memory. Thus, Contiki should be able to 
run on these devices. Contiki is an event-driven operating system which means that it responds when an event happens.
The main components of Contiki are the kernel, libraries, program loader, and a set of processes.

.. [DUNKELS2005] A. Dunkels, B. Gronvall, and T. Voigt, “Contiki - a lightweight and flexible operating system for tiny networked sensors,” in 29th Annual IEEE International Conference on Local Computer Networks, 2004, pp. 455–462.
