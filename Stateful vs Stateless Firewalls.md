Just a refresher on TCP/IP:
![[Pasted image 20250122123201.webp]]
- each connection has a request and response portion
- note the ephemeral and well known ports 

In a little more detail, to illustrate that **directionality depends on the perspective**:
![[Pasted image 20250122123509.webp]]


#### Stateless firewalls

These are firewalls that have no knowledge of the connection between various pieces of the communication

This means that when we are crafting firewall rules, each connection **needs 2**, one for the outgoing request and one for the incoming response. This applies whether your machine (server or client) the the one requesting OR responding:
![[Pasted image 20250122124052.webp]]
- remember that both inbound and outbound rules can be both **request AND reponse**, depending what you are doing
- always remember that when you are **responding**, you will need to allow the full range of ephemeral ports **because the firewall has no record of which ephemeral port came with the initial request**

### Stateful Firewalls

These firewalls can link requests and responses together, and craft the rules accordingly.

Usually you think in terms of the **request** (either way) and the **response will be allowed automatically**
- this means lower admin overhead

Imagining the same architecture with a stateful firewall:
![[Pasted image 20250122124306.webp]]
- note that ephemeral ports DON'T have to be all allowed, as the response is handled in reference to the request (which uses the well-known port)

