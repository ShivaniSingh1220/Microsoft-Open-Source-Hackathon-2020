# Microsoft-Open-Source-Hackathon-2020

### Problem statement: Smart Traffic Management system for Quick Commute and carbon reduction

                                                      Desciption
STMS Smart Traffic management system (based on Internet Of Things (IOT) for a single cross way intersection) is fully automated system which is used to dynamically change and control the Traffic Control light’s timer in a traffic intersection area.
Our Approach:
So, to overcome these shortcomings we propose new approach ‘Smart traffic management’ which is based on concept of IOT.
It is real-time traffic management system which is used to change traffic control lights depending upon the traffic congestion at that instant.
It can be also used for purpose of Traffic Monitoring.

      
    Let's understand the above mentioned problem statement
                                        
Smart traffic management technologies such as adaptive traffic control and traffic analytics can improve safety and significantly decrease traffic congestion levels and greenhouse gas (GHG) emissions.

The decentralized system uses a combination of video detection and radar to detect vehicle traffic and adjust signals in real-time using artificial intelligence-driven software. Results from the implementation have been substantial: 
* Travel times have been reduced by 26 percent, 
* wait times at intersections are down 41 percent and 
* vehicle emissions have been reduced by 21 percent.  

Smart traffic management systems are also enabling the development of smart intersections, which are emerging as one of the most important data-driven backbones needed to solve core city challenges.

Similar to the platform capabilities offered by smart street lighting, layers of additional services can be added to advanced traffic management systems, such as public transport prioritization and communications with connected vehicles.

For example, Microsoft is working with companies like Moovit and TomTom to offer critical real-time data to MaaS application providers, enabling them to deliver compelling applications. By connecting traffic lights, vehicles, people, and roads to the cloud, sharing data, embracing alternative modes of transportation, and building traffic management systems, cities like Hong Kong, Taipei, and Denver are experiencing success and leading the way for other cities. This connection is anticipated to enable a bus rapid transit route to be prioritized through targeted greenlight timing.

    Existing Techniques and flaws in these techniques
* In Field of Traffic Management System, many techniques and algorithms have been proposed and implemented to reduce traffic congestion.
Below are the few other solutions have we have seen in market? 
 
 Dynamic message sign monitoring and control: ###(A variable- (also changeable-,[1] electronic-, or dynamic-) message sign, often abbreviated VMS, CMS, or DMS, and in the UK known as a matrix sign,[2] is an electronic traffic sign often used on roadways to give travellers information about special events. Such signs warn of traffic congestion, accidents, incidents such as terrorist attacks, AMBER/Silver/Blue Alerts, roadwork zones, or speed limits on a specific highway segment. In urban areas, VMS are used within parking guidance and information systems to guide drivers to available car parking spaces... https://en.wikipedia.org/wiki/Variable-message_sign)

 Incident monitoring ###Traffic Incident Management is a planned and coordinated program process to detect, respond to, and remove traffic incidents and restore traffic capacity as safely and quickly as possible... https://ops.fhwa.dot.gov/eto_tim_pse/about/tim.htm)

 Active Traffic Management (ATM) ( Active traffic management (also managed lanes, smart lanes, managed/smart motorways) is a method of increasing peak capacity and smoothing traffic flows on busy major highways... https://en.wikipedia.org/wiki/Active_traffic_management) 

 Ramp meter monitoring and control ( A ramp meter, ramp signal, or metering light is a device, usually a basic traffic light or a two-section signal light (red and green only, no yellow) together with a signal controller, that regulates the flow of traffic entering freeways according to current traffic conditions... https://en.wikipedia.org/wiki/Ramp_meter)

 Arterial management ( Arterial Management strategies are used to effectively and successfully manage traffic and control arterial roadways... https://ops.fhwa.dot.gov/aboutus/one_pagers/arterial_mgmt.htm)

    There are mentioned flaws that we have see in those solutions?
 
* These techniques mainly uses Loop detector (Induction loop) circuits to calculate vehicle density. Once vehicle density is calculated , if it reaches some threshold value, it triggers the traffic light to change.  
 
* These are very outdated techniques which were developed in 1980’s. 
 
* Some of these approaches are also event driven and can’t be implemented for general traffic system. 
 
*Also, these systems are not deployed at every junction of the city/town. They are mainly used at most congested junctions of the area. Moreover, The new approaches being proposed does not define system which is fully automated and can behave with respect to traffic congestion at the junction in real time 


                          Our Approach
### So, to overcome these shortcomings we propose new approach ‘Smart traffic management’ which is based on concept of IOT. It is real-time traffic management system which is used to change traffic control lights depending upon the traffic congestion at that instant. It can be also used for purpose of Traffic Monitoring. 


    Proposed System 
# System requirements: 
 
1) High-end Server system. 
2) Internet Connection at every junction.  
3) Raspberry PI  
4) IP Cameras
 
Below is the block diagram for the proposed system, we are considering for a single crossway traffic intersection. 

    Smart Traffic Management System Block diagram 
 


# System Design: 
 
> The Proposed system is essentially a network of microcontrollers (Raspberry Pi) which are connected to a single main server. 
> These microcontrollers are installed at each traffic intersection points i.e. one microcontroller per junction. 
> Internet Protocol cameras are also installed for each traffic intersection junction. 
> The Microcontrollers are interfaced with Internet Protocol(IP) Camera and respective Traffic Control Signal lights. They are also connected to main server over Hyper Text Transfer Protocol (HTTP) through broadband connection. 
  
    Process flow:
    
 The IP Camera installed for each junction capture images at a fixed interval of time. These captures images are then forwarded to the corresponding interfaced Microcontroller. 

 The Microcontroller then uses Image Processing to calculate approximate traffic density for each junction. 

 The parameter traffic density is then forwarded to the main server where Traffic Control Signal optimization is used to calculate optimal Signal time for each Traffic control signal. 

 The server then sends the optimal signal time to microcontroller. 

 The microcontroller takes decision to allot maximum green signal time to corresponding control signal. 

 Thus, the optimal signal time is further forwarded from microcontroller to Traffic light who needs to be served. 

 The main server handles multiple requests from each junction and gives back optimal time for each junction using multithreading process. 
