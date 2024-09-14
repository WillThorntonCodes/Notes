Palo Alto has a high availability (HA) used for traffic failover and network redundancy. 

Hardware devices have dedicated ports used for HA named 
- HA1 Used for HA control and sync of traffic, uses management plane
- HA2 Used for HA session setup traffic
- HA3 Used for packet forwarding to peer firewall during session setup and asymentric traffic flow in active/active setup only.
- HSCI (High Speed Chassis Interconnect) can be used for HA2, HA3, or both types of traffic

Two types of deployment options Active/Standby or Active/Active
Active/Passive is easier to manage and deploy. Only one firewall is active at a time. Both share the same configuration and one will process traffic until there is a failure in the path, link, system, or network failure. Then the passive device becomes active. Virtual wire, layer2 and layer3 are supported. 

Active/Active is less common. Both are active processing traffic and work synchronously processing sessions. Each one maintains a session table and routing table. Virtual wire and layer3 are supported not layer2. DHCP client is not supported and the Active-primary firewall can function as DHCP relay. The active-secondary will drop DHCP broadcast packets.
