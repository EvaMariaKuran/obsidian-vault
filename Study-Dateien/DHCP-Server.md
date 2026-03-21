Der [[DHCP-Server]] verfügt über einen [[Pool]] von [[IP-Adressen]], die er den [[Client]]s zuteilen kann, welche die [[DHCP-Dienst]] nutzen. 
Der [[DHCP-Server]] muss zumindest bei größeren [[Netzwerk]]en wissen welche [[Subnetzmaske]] und [[Gateways]] (Standard) es gibt.
In der [[Regeln]] ist der [[DHCP-Server]] ein [[Router]] bzw. ein [[DHCP-Dienst]] direkt auf einem [[Server]]. 

Wenn ein [[Hosts]] mit einem aktivierten [[DHCP]]-[[Client]]  gestartet, so wird ein funktional eingeschränkter [[Modus]] das [[TCP/IP-Stacks]] gefahren. Dieser hat somit keine gültige [[IP-Adressen]], keine [[Subnetzmaske]] und kein (Standard-)[[Gateways]]. 
Das einzige, was der [[Client]] machen kann, ist [[IP-Broadcast]] verschicken. 

Nachdem der [[Client]] den [[IP-Broadcast]] verschickt hat, was als [[DHCP-Discover]] bezeichnet wird, bekommt er eine Antwort von dem [[DHCP-Server]] ([[DHCP-Offer]]). 
Darauf folgt ein [[DHCP-Request]] und ein [[DHCP-Acknowledgement]].
