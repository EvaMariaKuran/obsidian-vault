Sub ErstelleInhaltsverzeichnisAusSpalten()

    Dim ws As Worksheet
    Dim toc As Worksheet
    Dim lastCol As Long
    Dim i As Long
    Dim rowIndex As Long
    Dim header As String

    Application.ScreenUpdating = False

    ' Erstes Blatt als Inhaltsverzeichnis verwenden
    Set toc = ThisWorkbook.Sheets(1)
    toc.Cells.Clear

    toc.Range("A1").Value = "Inhaltsverzeichnis (Spaltenüberschriften)"
    toc.Range("A1").Font.Bold = True

    rowIndex = 3

    ' Alle Blätter durchgehen
    For Each ws In ThisWorkbook.Worksheets

        If ws.Name <> toc.Name Then

            toc.Cells(rowIndex, 1).Value = "Blatt: " & ws.Name
            toc.Cells(rowIndex, 1).Font.Bold = True
            rowIndex = rowIndex + 1

            ' letzte genutzte Spalte in Zeile 1
            lastCol = ws.Cells(1, ws.Columns.Count).End(xlToLeft).Column

            For i = 1 To lastCol

                header = ws.Cells(1, i).Value

                If header <> "" Then
                    toc.Cells(rowIndex, 1).Value = header
                    toc.Cells(rowIndex, 2).Value = ws.Cells(1, i).Address(False, False)

                    ' Hyperlink zum Blatt
                    toc.Hyperlinks.Add _
                        Anchor:=toc.Cells(rowIndex, 1), _
                        Address:="", _
                        SubAddress:="'" & ws.Name & "'!" & ws.Cells(1, i).Address, _
                        TextToDisplay:=header
                End If

                rowIndex = rowIndex + 1

            Next i

            rowIndex = rowIndex + 1 ' Abstand zwischen Blättern
        End If

    Next ws

    toc.Columns("A:B").AutoFit

    Application.ScreenUpdating = True

    MsgBox "Inhaltsverzeichnis wurde erstellt.", vbInformation

End Sub


#informatik #Microsoft365 #Microsoft365/Excel #informatik/Skripte 