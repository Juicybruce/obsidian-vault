A conceptual model divided into 7 layers within a **networking stack**
Host Layers (how the data is divided and formatted for understanding by both sides)
- Application
- Presentation
- Session
- Transport
Media Layers (dealing with how data is *moved*)
- Network
- Datalink
- Physical

All layers utilise the layers below them, but these lower layers are **abstracted**. A web browser (layer 7) will communicate with a web-server on the same layer, but does not need to itself mediate the other layers, that is handled by each layer as they are used by that transmission as a whole

![[OSI Model image.png]]

#### Physical - Layer 1

Describes the base physical medium that enables transmission of **raw bitstreams** of unstructured data.

This standard defines everything from voltages, distances, modulations etc so any layer 1 device can understand this **raw data**.

At layer 1, there is **no addressing**, all data is broadcasted to all devices that are linked on a layer 1 connection. There is no **media access control**, ie, any device can transmit whenever, meaning collisions (and loss of data due to them) are basically guaranteed.

#### Data Link - Layer 2

This provides a bulk of the important archtecture for the **reliable transfer of data between to node on a network layer** most of the other layers rely on.

Introduces **frames** which encapsulate data to be sent and error checked:
- Preamble - start of the frame
- Destination/source address (MAC)
- Ether type - specify what layer 3 protocol is using this frame
- Payload - actual data (46-1500 bytes)
- Frame Check Sequence - allows for data integrity 

Also introduces MAC addresses for addressing specific pieces of hardware

Data link also mediates the access control, ie, when each node is allowed to talk:
- a node can build a frame and then check the physical layer for a **carrier signal** that indicates something is already being sent, and will wait if that is the case
- Collision detection will trigger a **backoff** with a random period of time where all devices stop transmitting, then hopefully when they retry, one will get in first, and the others will see their carrier signal

At layer 2 we have 
- identifiable devices
- media access to control (to prevent collisions)
- detection of collisions if they do occur
- Unicast and broadcast communication

### Net



#networking #sysadmin 