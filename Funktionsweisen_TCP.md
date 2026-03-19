Die [[Verbindungen]] zwischen den [[Geräte]]n die hergestellt wurden, werden automatisch aufrechterhalten bis die [[Anwendungen]] auf beiden Seiten den Austausch von [[Nachrichten]] beendet haben. 
Folgend werden die Aktionen aufgezählt welche [[TCP]] durchführt um eine aktive [[Verbindungen]] der [[Geräte]] zu haben, welche aufrechtgehalten werden. 

- Zuerst wird durch ein [[Drei-Wege-Handshake]], bei dem [[Sender]] und [[Empfängern]] [[Steuerpakete]] ([[Control Packets]]) ausgetauscht, um sich zu synchronisieren und eine [[Verbindungen]] herzustellen. 
- Nun wird festgelegt, wie die [[Anwendungsdateien]] in [[Pakete]] zerlegt werden, welche über das [[Netzwerk]] übertragen werden können. 
- Schließlich werden [[Pakete]] an die [[Netzwerkschicht]] gesendet und diese nimmt die [[Pakete]] entgegen. 
- verwaltet somit die [[Flusskontrolle]]
- Kümmert sich zusätzlich um die erneute [[Übertragungen]] von verworfenen oder verstümmelten [[Pakete]]n, um eine fehlerfreie [[Datenübertragung]] zu gewährleisten. 
- Bestätigt alle ankommenden [[Pakete]]
- beendet die [[Verbindungen]] nach Abschluss der [[Datenübertragung]] durch einen [[vierfachen Handshake]]. 
So deckt auch [[TCP]] im [[OSI-Modells]] ([[OSI-Kommunikationsmodell]]) Teile von [[Schicht 4]], der [[Transportschicht_OSI]], und Teile von [[Schicht 5]], der [[Sitzungsschicht_OSI]] ([[Session Layer]]), ab.

Anwendungsbeispiel: 
	Wenn ein [[Webserver]] eine [[HTML]]-[[Dateien]] an einen [[Client]] sendet, verwendet er dazu [[HTTP]]. Die [[HTTP-Programmierschicht]] fordert die [[TCP-Schicht]] auf, die [[Verbindungen]] aufzubauen und die [[Dateien]] zu senden. 
	Der [[TCP-Stack]] teilt die [[IP-Schicht]] zur Zustellung weiter. 
	Obwohl jedes [[Pakete]] bei der [[Übertragungen]] dieselbe [[Quell-IP-Adresse]] und [[Ziel-IP-Adresse]] hat, können die [[Pakete]] über mehrere [[Routen]] gesendet werden. 
	Die [[TCP-Programms]] ([[Program Layer]]) auf dem [[Client]]-[[Computer]] wartet, bis alle [[Pakete]] eingetroffen sind. Dann bestätigt sie die empfangenen [[Pakete]] und bittet um die erneute [[Übertragungen]] der [[Pakete]], die sie nicht erhalten hat, basierend auf den fehlenden [[Paketnummern]]. Die [[TCP-Schicht]] setzt dann die [[Pakete]] zu einer [[Dateien]] zusammen und übergibt die [[Dateien]] and die empfangende [[Anwendungen]]. 
