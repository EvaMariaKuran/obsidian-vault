Der [[SQL-Befehlen]] fügt Informationen bzw. eine neue [[Zeile]] bei der [[Tabelle]] ein. Die [[Tabelle]] heißt in diesem Fall "tablename".  Bei dieser Art von Befehl ist es wichtig zu wissen, dass man alle [[Spalten]] in den Klammern, mit den Informationen füllt, welche man auch einfügen mag. 
Ein anderer Befehl mit einer weiteren Funktion ist der [[insert into tablename (.1.) values (.2.);]]


Dieser Befehl könnte Beispielsweise so aussehen: 
INSERT INTO Bank VALUES ('GENODEF1VRR','Volksbank','Rosenheim'); 

![[Pasted image insert into - Befehl einfach.png]] 

Natürlich kann man auch mehrere Zeilen in einem Befehl einfügen: 
INSERT INTO Bank VALUES ('GENODEF1VRR','Volksbank','Rosenheim'), ('GENODEF3VRK', 'Volksbank', 'Kolbermoor'); 

![[Pasted image insert into Befehl.png]] 

Der Befehl in ein paar [[Programmiersprachen]], wie in  [[SQL]] oder [[Java]] endet [immer] mit einem [[Selekolumn]] [;] 
