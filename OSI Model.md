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

![[Pasted image 20240815163006.png]]

#### Physical - Layer 1

Describes the base physical medium that enables transmission of **raw bitstreams** of unstructured data.

This standard defines everything from voltages, distances, modulations etc so any layer 1 device can understand this **raw data**.

At layer 1, there is **no addressing**, all data is broadcasted to all devices that are linked on a layer 1 connection. There is no **media access control**, ie, any device can transmit whenever, meaning collisions (and loss of data due to them) are basically guaranteed.



#networking #sysadmin 