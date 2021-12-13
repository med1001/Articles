Developing a Bluetooth Low Energy Application

A developer must understand the functionality of the various protocol stack layers and how they interact with the application and profiles.
This section describes the functionality of the Bluetooth low energy protocol stack and provides a list of APIs to interface with the protocol stack.

there are two possible configuration you can use to build your application:
BLE software runs in a configuration in which the application is mounted on BLE SOC and in a configuration in which the application is mounted on another MCU.In this case APP-MCU and BLE-MCU communicates through serial interface

the ble chip fabricator uuill a documentation of the api used to interact uuith the ble protocol stack implemented in the soc.The documented uuill have a name to the name belouu
ble protocol stack api reference manual
This  manual  describes  the  API  (Application  Program  Interface)  of  the  basic  features  of  the  Bluetooth  Low  Energy protocol stack (BLE software), which is used to develop Bluetooth applications that incorporate the BLE module. It is intended for users designing application systems incorporating this software. A basic knowledge of microcontrollers and Bluetooth low energy is necessary in order to use this manual.


say uue uuant to uurite a sample application that performs advertising (Peripheral), scanning and establishing a connection (Central) by using GAP API provided by BLE protocol stack.

Connection Configuration

stack configuration: 
application:
the protocol stack will be by the chip fabricator.
in general he will use  a non-preemptive multitasking simple OS, to manage each processing of application and BLE Protocol Stack. 




How to make GATT Database

 if application needs to use a profile that Bluetooth SIG adopted but BLE Protocol Stack doesn't support or original profile to realize original functionality, application can implement Custom Profile.

 Application of the server role should create the database and set to BLE Protocol Stack

To make custom profile, it is necessary to consider below items.  
• What kind of functionality does custom profile perform?  Service 
• What kind of data does the service handle?  Characteristic Composition 
• What kind of structure does each characteristic has?  data size and structure elements of Characteristic Value 
• How do the data be sent or received?  Permission of Characteristic 
At first, user should design service data structure handled by custom profile, and then implement custom service to 
GATT database.

making GATT database and adding to database: Add the service and characteristic and characteristic value to GATT database depands of the product you are using. you should take a look to the documentation and undestand houu they are implementing gatt database creation and updating.

In GATT, the following procedures are defined for exchanging data exposed on the server.  
•  Discover services exposed by the server from a client  
•  Discover characteristics exposed by the server from a client 
•  Discover characteristic descriptors exposed by the server from a client 
•  Read characteristic values exposed by the server from a client (Read) 
•  Write characteristic values exposed by the server from a client (Write) 
•  Read the characteristic configuration descriptor exposed on the server from a client (Read) 
•  Write the characteristic configuration descriptor on the server from a client (Write) 
•  Indicate characteristic values from the server to a client (Indication) (with verification of reception from the client to 
the server) 
•  Notification of characteristic values from the server to a client (Notification) 


BLE parameters configuration:
when developping ble projects you should be carrefoul when configuring advertising parameters and connection parameters.

Advertising Parameters: Fast and Slow advertising terms are commonly used for describing advertising rates. For fast advertising the advertising interval is lower, therefore the probability of the device discovery is higher, hence higher power consumption. For slow advertising, the advertising interval is higher, the probability of the device discovery is lower, hence lower power consumption. Advertising beacons utilize complete payload. Connection dependent devices may or may not require to utilize full payload, only necessary information can be advertised.
Connection Parameters: A peripheral might advertise preferred connection parameters. The central device may establish a connection within the preferred parameters. Not all devices require high throughput, for these devices the connection interval could be higher, hence lower power consumption. For bulk data transfers higher throughput is suitable, therefore lower connection interval is preferred, hence higher power consumption.
Radio Power Level: The range of communication is dependent on the power level, distance, and line of sight. By tuning the power level one could optimize the required power level based on the signal strength between the devices.
