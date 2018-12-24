# Data Link Layer
- It is responsible for moving of data into and out of physical link in a network. 
- Data bits are encoded, decoded and organized in the data link layer before they are transferred between the nodes.
- The data link layer ensures an initial connection has been set up, divides output data into data frames and handles the acknowledgements from a receiver that the data arrived successfully. It also ensures incoming data has been received successfully by analyzing bit patterns at special places in the frames.
- If an error occurs, the data link layer notifies higher-level protocols that something has happened to the physical link. Frame sequencing capabilities within the data link layer permit the receiving device to reorder frames that might have been transmitted out of sequence. The data link layer verifies the packet is unimpaired. The data link layer also manages flows by enabling devices on a link to detect congestion. Nearby devices then transmit congestion information, so traffic can be rerouted accordingly.
## Ethernet and Mac Addresses
### Ethernet 
The protocol most widely used to send data across individual links.

Data link layer provides an abstraction. It abstracts away the complexity of physical layer. For example, the web browser we are
using in our computer is not aware of the physical layer components like whether there is a twisted cable or something else.

### Mac Address:
A globally unique identifier attached to an individual network interface. Mac addresses are linked to the hardware while IP address 
is linked to the software.

Whether we use wireless internet or wired internet, both takes network software and hardware (cables, routers etc.) to tranfer data 
from one computer to another or between two computer thousands miles apart. To get the data we need addresses. Hence along with IP 
address we also have a hardware address called MAC address. Our computer has a NIC card that makes possible to connect our computer
to a network. NIC turns data into electric signals that can be transferred though the cables.
