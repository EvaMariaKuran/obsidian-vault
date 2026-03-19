Da das [[DHCP-Acknowledgement]] die [[Lease-Time]] enthält, welche dem [[Client]] die zugewiesene [[IP-Adresskonfiguration]] mitteilt wie lange er diese verwenden kann und darf. 
Nach der Hälfte  der [[Lease-Time]] muss der standardkonforme [[Client]] einen erneuten [[DHCP-Request]] sendet. 
In der [[Regeln]] wird der [[DHCP-Server]] ein [[DHCP-Acknowledgement]] mit identischen [[Daten]] und einer aktualisierten [[Lease-Time]] schicken. 
Damit gilt die Nutzung der [[IP-Adressen]] als verlängert. 

Aber was ist, wenn der [[DHCP-Server]] nicht antwortet und somit die aktuelle [[IP-Adresskonfiguration]] nicht bestätigt/verlängert wird? 
Wenn der [[DHCP-Server]] ausgefallen ist oder ähnliches war, dann läuft die [[IP-Adresskonfiguration]] normal weiter bis diese auslaufen soll. 
Kurz vor dem Auslauf schickt der [[Client]] nochmals einen  [[DHCP-Request]] und wartet auf eine Antwort. 
Wenn dieser nicht mehr antwortet, da ein neuer [[Server]] installiert wurde, dann versucht der [[Client]] mit einem [[DHCP-Discover]] eine neue [[IP-Adresskonfiguration]] von dem neuen [[Server]] zu erhalten. 
