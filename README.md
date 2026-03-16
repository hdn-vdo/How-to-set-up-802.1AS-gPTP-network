# How-to-set-up-802.1AS-gPTP-network

Abstract:
802.1AS gPTP boundary clock (BC), gPTP clock bridge, gPTP endpoint.
LinuxPTP Master clock and Slave clock.


# 802.1AS gPTP boundary clock (BC): 
SW2000M TSN Swtich, set Port 9 as gPTP Slave and others ports as gPTP Master.


# gPTP Grandmaster: 
Orin nano or AGX or NX, set as the gPTP Master clock, connect to SW2000M TSN Port 9.


Command: sudo ptp4l -H -m -i eno1 -f automotive_Master.cfg

# gPTP endpoint(slave):
LinuxPTP with Slave clock, connect to SW2000M TSN Port 1 via a 100/1000BASE-T1 Media convertor(MC1100).


Command: sudo ptp4l -H -m -i eno1 -f automotive_Slave.cfg


*Linux PC Network Adapter must support IEEE1588, such as Intel I210,I217,I218,I219,I225 Network Adapter. 


# gPTP endpoint(slave):
Lidar, (Such as AT128 or M1P Lidar). gPTP slave clock. connect to SW2000M TSN Port 2 to Port 5...


# gPTP endpoint(slave):
other cotrol unit, set as gPTP slave clock, connect to SW2000M TSN other ports.

# Complete
Now, the sample gPTP network set up done.
