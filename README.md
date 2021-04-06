# **EE450 Socket Programming Project** <br>
## **Personal Information** <br>
Full Name: Ziwei Jia<br>
USC ID: 2085454571<br>

## **What I have done in this assignment** <br>
In this project, I have implemented a system to deal with resource allocation based on client queries for COVID-19. <br>

**Phase 1 Boot up the hospitals and scheduler** <br>
  - Scheduler set up the UDP socket and wait for the boot-up message from hospitals. 
  - Hospital A, B and C read the map.txt and construct the location graph. 
  - Construct a data structure to store the capacity and occupancy of hospitals for book-keep the availability of hospitals.

**Phase 2 Forward stage**<br>
  - The client send the query to the scheduler server.
  - The Scheduler server receive the query and decide the hospitals that still have availablity. <br>
  

**Phase 3 Scoring**<br>
  - The scheduler construct a input message and send it to the available Hospitals.
  - Each available hospital receive the client location information and run Dijkstra  algorithm find the shortest path.
  - Hospital server combine the distance and availability to get the final score.
  - Hospital server send the score to the scheduler.

**Phase 4 Reply**<br>
  -

