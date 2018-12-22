# Transport Layer 
 - Transport layer is responsible for taking the application messages and transmits those message segments into the network layer.
 - The receiving side prepares the response segment of the request from the application. Then this segment is passed to the application 
 layer by the transport layer.
 - Transport layer provides two types of mode for communication:
   - Connection mode transmission
   - Connectionless mode transmission

## Connection mode transmission (**TCP: Transmission Control Protocol**)
 - In connection mode transmission, a transmission may be sent or arrive in the form of packets (A packet is the unit of data that is 
 routed between an origin and a destination. TCP protocol layer divides the file into "chunks" of an efficient size for routing.
 Each of these packets is separately numbered and includes the IP address of the destination. These individual packets might take
 different route and then are reassembled together into the original file (by the TCP layer at the destination end). Connection 
 mode transmission also requires assurance from the receiving device. 
 - TCP is the most common connection mode transmission. The connections are identified and tracked using the port numbers ranging from 
 0 to 65535.
 - If the receiver end in TCP protocol doesn't send the assurance message back to the sender, then the sender tries to resend the data.
 - TCP segment is present in the Ethernet. TCP segment is made up of TCP header and a data section. The data section is another payload
 area where the application layer places its data. TCP header is split into several other fields. Source port and destination port 
 are the present in the begining of the header. Next field is the sequence number which helps in maintaining the orders. The next field is 
 the acknowledgement section. Next is data offset field. Next are TCP control flags Next is TCP window and this window specifies the range 
 of sequence numbers that might be sent before an acknowledgement is required. Next field is the checksum field which checks for data integrity.
 - TCP flags
 (a) URG: Urgent flag -> If it is set to 1 then it means that the segment is considered urgent.
 (b) ACK: Acknowledgement flag -> If it is set to 1 then it means that acknowledgement number field need to be examined.
 (c) PSH: Push flag -> Transmitting device wants the receiving device to push currently-buffered data to the application on the 
 receiving end as soon as possible.
 (d) RST: Reset flag -> It helps in resetting the whole process when the meaningful data is not received by the receiver.
 (e) SYN : Synchronization flag -> Synchronizes with the receiver to make sure that receiver end knows how to examine the sequence number.
 (f) FIN : Finish flag -> If this flag is one that menas the transmitting end has nothing more to send and the connection can be closed.
 
 Example:
 
 For a good example of how TCP control flags are used, let's check out how a TCP connection is established. 
 Computer A will be our transmitting computer and computer B will be our receiving computer. 
 To start the process off, computer A, sends a TCP segment to computer B with this SYN flag set. 
 This is computer A's way of saying, "Let's establish a connection and look at my sequence number field, 
 so we know where this conversation starts." 
 Computer B then responds with a TCP segment, where both the SYN and ACK flags are set. 
 This is computer B's way of saying, "Sure, let's establish a connection and I acknowledge your sequence number." 
 Then computer A responds again with just the ACK flag set, which is just saying, "I acknowledge your acknowledgement. 
 Let's start sending data." I love how polite they are to each other. 
 This exchange involving segments that have SYN, SYN/ACK and ACK sets, happens every single time a TCP connection is established anywhere. 
 And is so famous that it has a nickname. The three way handshake. 
 A handshake is a way for two devices to ensure that they're speaking the same protocol and will be able to understand each other. 
 Once the three way handshake is complete, the TCP connection is established. 
 Now, computer A is free to send whatever data it wants to computer B and vice versa. 
 Since both sides have now sent SYN/ACK pairs to each other, a TCP connection in this state is operating in full duplex. 
 Each segment sent in either direction should be responded to by TCP segment with the ACK field set. 
 This way, the other side always knows what has been received. 
 Once one of the devices involved with the TCP connection is ready to close the connection, something known as a four way handshake happens. 
 The computer ready to close the connection, sends a FIN flag, which the other computer acknowledges with an ACK flag.
 Then, if this computer is also ready to close the connection, which will almost always be the case. 
 It will send a FIN flag. This is again responded to by an ACK flag. Hypothetically, a TCP connection can stay open in simplex mode with only one side closing the connection.
 
 
 ## Connectionless mode transmission (**UDP: User Data Protocol**)
 - In connectionless mode transmission, a transmission may be sent or arrive in the form of datagrams. Datagram is a self-contained
 independent entity of data carrying sufficient information to be routed from the source to the destination without reliance on earlier
 exchange between the source and the destination computer and the transporting network. **UDP** is an example of connectionless mode transmission. It uses port numbers between 0 and 65,535. But it is not similar to TCP
 because it doesn't require an assurance from the receiver. Hence, UDP is better for real-time streaming data transmissions like voice
 and video conferencing. 
 
 The features supported are:
 
   - same order delivery: order of the packets are maintained
   - data integrity: ensures that data is not corrupted 
   - flow control
   - congestion avoidance
   - multiplexing: helps situations like when the users open different browser in the same computer
 
