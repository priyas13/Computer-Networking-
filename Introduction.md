## Introduction to Networking 
Humans follow a way to communicate. Similarly computers also need a set of rules to communicate with us or the network.
* **Protocol** : A defined set of standards that computers must follow in order to communicate properly.
* **Computer networking** : Full scope of protocols defining how computers communicate with each other.
## TCP/IP Five-Layer Network Model
* **Physical** (Bottom layer) : It represents the physical layer that interconnects computers. Physical layer is all about cabling, connector, sending signals. This includes:

  (1) Specification for the networking cables and the connectors that join devices together 

  (2) Specification about how signals are sent over these connections.

* **Data Link** (Second layer from bottom) : It is responsible for defining a comman way of interpreting these signals so network devices can communicate. Lots of protocal exists means lots of rule for communication exists but the most common one is *Ethernet*. The first protocol is defined in the Data link layer. *Ethernet* also defines the specification of the physical layer and also defines  protocols responsible for getting data to nodes on the same network or link. Data link layer is responsible for getting the data across a single link.

* **Network Layer** (Also called Internet layer) : It allows different networks to communicate with each other through devices known as routers. A collection of networks connected through routers are caller *Internetwork*, the most famour example is *Internet*. Network layer is responsible for getting a data delivered across a collection of networks.

  As we all use internet in our houses, when a device on our homw network connects with a server on the internet, it is the     network layer that helps to get the data between these two location (device and the server).

  The most common used protocol in this layer is *IP* (Internet protocol). Network layer delivers data between two nodes. 

* **Transport Layer** As we have seen above, network layer is only responsible for transferring data between two nodes. But there might be the case that there are various client application running on a single node that is accessing the same server for internet. For exmaple, we are running email application and a web browser on a pc at the same time which are running on the same server. Netwrok layer delivers data between the server and the pc, but it is the job of the transport layer to distribute the data among the clients on the same node.

  *This layer sorts out which client and server programs are supposed to get that data*
  
  The most common protocol in this layer is *TCP*
  
 * **Application Layer** There are lots of different protocols used in this layer. Users interact directly with this layer like http, git etc.
