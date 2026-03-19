[[ICMP]] nutzt den [[Standard-IP-Header]] zur [[Übertragungen]] von [[Meldungen]] genutzt.
Die Felder des [[Standard-IP-Header]]s werden bei der [[Nutzung_ICMP]] angepasst. 

Folgende Felder werden bei der [[Nutzung_ICMP]] angepasst:
	Das Feld [[Type-of-Service]] wird auf den Wert "0000" gesetzt.
	Das [[IP-Header-Feld]] [[Protokoll]] wird auf den Wert "0001" (=[[ICMP]]) gesetzt. 
	Der [[Daten-Bereich]] des [[IP-Header]]s wird zum [[ICMP-Bereich]]. 
		Der [[Daten-Bereich]] wird auch nur zum [[ICMP-Bereich]], wenn folgende Felder angepasst:
			- [[ICMP-Typ]] ([[Meldungstyp]])
			- [[ICMP-Code]] ([[Zusatzinformationen zur Behandlung der Nachricht]])
			- [[ICMP-Check-Summe]]
			- [[ICMP-Daten-Bereich]] 
				- Dieser Bereich enthält den [[IP-Header]] und die ersten 64 [[Bits]] [[IP-Daten]] des [[IP-Pakets]], dass die [[ICMP-Meldung]] ausgelöst hat. 
- 