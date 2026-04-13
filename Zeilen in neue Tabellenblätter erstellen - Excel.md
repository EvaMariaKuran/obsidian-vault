Sub ZeilenInNeueBlaetterKopieren()
    Dim wsQuelle As Worksheet
    Dim wsNeu As Worksheet
    Dim lastRow As Long
    Dim i As Long
    Dim zeilenProBlatt As Integer
    
    '--- KONFIGURATION ---
    Set wsQuelle = ActiveSheet ' Die Tabelle mit den Daten
    zeilenProBlatt = 1         ' Wie viele Datenzeilen pro neues Blatt?
    '---------------------
    
    ' Letzte Zeile der Quelle finden
    lastRow = wsQuelle.Cells(wsQuelle.Rows.Count, "A").End(xlUp).Row
    
    ' Schleife durch die Zeilen (startet bei 2, wenn Header in Zeile 1 ist)
    For i = 2 To lastRow Step zeilenProBlatt
        ' Neues Blatt am Ende einfügen
        Set wsNeu = Worksheets.Add(After:=Worksheets(Worksheets.Count))
        
        ' Neues Blatt benennen (basierend auf Spalte A, Zeile i)
        wsNeu.Name = "Daten_" & wsQuelle.Cells(i, 1).Value
        
        ' Header kopieren (optional)
        wsQuelle.Rows(1).Copy Destination:=wsNeu.Rows(1)
        
        ' Datenzeile(n) kopieren
        wsQuelle.Rows(i & ":" & i + zeilenProBlatt - 1).Copy Destination:=wsNeu.Rows(2)
    Next i
    
    wsQuelle.Activate
    MsgBox "Neue Tabellen wurden erstellt!", vbInformation
End Sub


#informatik #informatik/Programme #informatik/Skripte #Microsoft365 #Microsoft365/Excel 