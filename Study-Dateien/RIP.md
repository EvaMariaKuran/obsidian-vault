Das [[RIP]] ist ein [[Distance-Vector-Algorithmus]], also ein [[Distance-Vector-Routing-Protokoll]]. 
Es ist das einfachste und meist genutzte [[Protokoll_Routing]]. Die [[Fähigkeiten]] moderner [[Netzwerk]]e werden von [[RIP]] allerdings nicht berücksichtigt. 

[[Routing Information Protocol]] notiert sich im einfachsten Fall in der [[Routing-Tabelle]] neben der [[Netzwerkadressen]] und abgehende [[Schnittstellen]] nur die Anzahl der Stationen ([[Hops]]) die ein [[Datenpaketen]] bis zum [[Zielnetz]] überwinden muss. 

Bei einem [[Hop-Eintrag]] von 16 ist es unendlich lang und somit nicht erreichbar. Daraus schließt sich, dass ein [[Netzwerk]] mit mehr als 15 Zwischenstationen nicht geeignet. 
Dadurch wird das [[Routing Information Protocol]] nur in lokalen [[Netzwerk]]en verwendet, wo die [[Netzübergänge]] von gleicher [[Qualität]] bleibt und die [[Netzwerkstruktur]] nur selten verändert wird.

Die [[Router]] tauschen sich alle 30 Sekunden mit einander aus und somit sind die [[Routing-Tabelle]] aktuell. 
Durchaus führt dies zu einem erhöhten [[Datenverkehr]] zwischen den [[Routern]]. Fällt einer aus, kann es durchaus mehrere Minuten dauern, bis diese Information und die entsprechend geänderte [[Routing-Tabelle]] übermittelt wurden. 
