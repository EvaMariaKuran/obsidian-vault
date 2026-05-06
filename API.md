Application Programming Interface = Programmierschnittstelle 

- definierte Schnittstelle 
- 2 Softwarekomponenten kommunizieren miteinander 
	- keiner muss von den anderen wissen, wie sie intern funktionieren
	- "Vertrag zwischen Systemen"

> APIs sind das Nervensystem moderner IT-Architekturen. Ohne sie würden kaum zwei Systeme miteinander reden können.
> 
> Eine API ist die vereinbarte „Tür", durch die Software mit anderer Software kommuniziert – geregelt, sicher und ohne interne Details preiszugeben.
#### Analogie
Stell dir ein Restaurant vor: Du (Client) bestellst beim Kellner (API), was du willst. Die Küche (Server/System) bereitet es zu. Du weißt nicht, wie die Küche funktioniert – du brauchst nur die Speisekarte (API-Dokumentation) zu kennen.

#### Kernidee
- verbirgt interneKomplexität 
- Funktionen/Daten Anfrage --> Was
- Format/Parameter Anfrage --> Wie
- Antwort 
	- Bereitstellung nur von dem tatsächlichen Gebrauchten


> Anbieter kümmert sich um alles dahinter - Nutzer kennt nur die Schnittstelle > 

#### Warum APIs so wichtig sind
- **Modularität** – Systeme können unabhängig entwickelt und ausgetauscht werden
- **Wiederverwendbarkeit** – dieselbe API kann von vielen Clients genutzt werden
- **Sicherheit** – nur definierte Zugriffspunkte sind exponiert, nicht das ganze System
- **Skalierbarkeit** – Backend und Frontend lassen sich getrennt skalieren

#### Gängige API-Typen in der IT

- **REST-API** – der heutige Standard; nutzt HTTP-Methoden (GET, POST, PUT, DELETE), antwortet meist mit JSON
- **SOAP-API** – älterer Standard, XML-basiert, noch häufig in Enterprise-Systemen (z. B. SAP)
- **GraphQL** – flexibler als REST; der Client bestimmt selbst, welche Felder er haben will
- **Bibliotheks-API** – z. B. Windows API oder .NET-Klassen, die du im Code direkt aufrufst (kein Netzwerk nötig)
- **Betriebssystem-API** – Programme sprechen mit dem OS, um Dateien zu öffnen, Prozesse zu starten etc.
- **WebSocket-API** – für Echtzeit-Kommunikation (z. B. Chat, Live-Dashboards)
- **Interne APIs** – verbinden Microservices oder Systeme innerhalb einer Organisation
- **SDK/Library-APIs** – Programmierschnittstellen innerhalb einer Sprache (z. B. Windows API, .NET)


#informatik #informatik/Programme #informatik/Syncronisationen 