Der [[TCP-Stack]] ist ein [[Modelle]], das darstellt, wie [[Daten]] über [[Netzwerk]]e mit dem [[TCP/IP]]-[[Protokoll]] organisiert und ausgetauscht werden. 
Es zeigt eine Reihe von Schichten, die die Art und Weise darstellen, wie [[Daten]] auf ihrem Weg vom [[Client]] zum [[Server]] und umgekehrt von einer Reihe von [[Protokoll]]en behandelt und verpackt werden. 
[[TCP]] existiert in der [[Transportschicht]] mit anderen [[Protokoll]]en wie [[UDP]]. 
Die [[Protokoll]]e dieser Schicht sorgen für die fehlerfreie [[Übertragungen]] der [[Daten]] zur [[Quelle]], mit Ausnahme von [[UDP]], da es nur über eine begrenzte [[Fähigkeiten]] zur [[Fehlerkontrolle]] verfügt. 

Dieses [[Modelle]] ist ein [[konzeptionelles Modell]] wie das [[OSI-Modells]], welches für die [[Datenaustauschstandards]]. 
Die [[Daten]] werden auf jeder einzelnen Schicht auf die Grundlage ihrer Funktionalität und der [[Transportprotokolle]] neu verpackt.

Die [[Daten]] bewegen sich auf die folgenden Arten: 
- Sie bewegen sich von der [[Anwendungsschicht]] zur [[Transportschicht]], wo sie in [[TCP-Segmente]] 
- Sie werden zur [[Internet-Schicht_TCP]] transportiert, wo sie in ein [[Datagramm]] umgewandelt werden
- Sie werden zur [[Netzwerkschnittstellenschicht]] übertragen, wo sie wieder in [[Bits]] und [[Frames]] zerlegt werden. 
- Wenn der der [[Server]] antwortet, durchlaufen sie den [[TCP-Stack]], um als [[Daten]] auf der [[Anwendungsschicht]] anzukommen.
