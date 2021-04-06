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
  - Hospital server send the score to the scheduler.<br>
  
**Phase 4 Reply**<br>
  - Scheduler gets the result from the Hospital server and sorts the distance and score.
  - Scheduler reply the final result message to client and also send a message to the selected Hospital
  - The selected Hospital server updates its information (capacity, occupancy).

## **Code Files** <br>

**client.cpp** <br>
  - Receive client location parameter. 
  - Create the TCP socket and connect to the scheduler server.
  - Send the client location message to scheduler server and receiver the result.

**scheduler.cpp** <br>
  - Creat TCP and UDP sockets for client and hospitals.
  - Receive the boot up messages(capacity and occupancy) from the hospital.
  - Receive the client input and send it to the selected hospital.
  - Get the results from the hospitals and compare the results.
  - Send the final result to client and the selected hospital server.
  

**hospitalA.cpp** <br>
  - Read the map.txt and construct the location graph. 
  - Set up the UDP socket and receive the client input data from the hosptial server.
  - Calculate the shortest distcance between client location and server location by Dijkstra algorithm.
  - Calculate the Score and return it back to the scheduler server.
  
**hospitalB.cpp** <br>
  - Read the map.txt and construct the location graph. 
  - Set up the UDP socket and receive the client input data from the hosptial server.
  - Calculate the shortest distcance between client location and server location by Dijkstra algorithm.
  - Calculate the Score and return it back to the scheduler server.

**HospitalC.cpp** <br>
  - Read the map.txt and construct the location graph. 
  - Set up the UDP socket and receive the client input data from the hosptial server.
  - Calculate the shortest distcance between client location and server location by Dijkstra algorithm.
  - Calculate the Score and return it back to the scheduler server.

**Makefile** <br>
  - Execute the set of the tasks above.
  
## **Message exchange** <br>

**Between Client and Scheduler** <br>
  - The client sent the client location message (string) like "123" to scheduler server.  
  - Scheduler send the final result (string) like "A" to client. 

**Between Scheduler and Hospital**<br>
  - The scheduler send the client location message (string) like "123" to scheduler server.
  - Hospitals send the boot-up message (string) include capacity and occupancy like "456|789".
  - Hospital send the score and distance message (string) like "0.0056|670.467317631".
  - Scheduler send the final result message (string) like "Increase the occupancy" to the selected hospital.
  
## **Idiosyncrasy** <br>

## **Reuse Code** <br>
