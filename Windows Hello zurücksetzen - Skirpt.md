# --- Konfiguration ---
$NgcPath = "C:\Windows\ServiceProfiles\LocalService\AppData\Local\Microsoft\NGC"

Write-Host "=== Windows Hello (PIN) Reset Script ===" -ForegroundColor Cyan

# --- Prüfen, ob NGC existiert ---
if (-Not (Test-Path $NgcPath)) {
    Write-Host "NGC-Ordner existiert nicht. Kein Windows Hello aktiv." -ForegroundColor Yellow
    exit
}

# --- Inhalt prüfen ---
$items = Get-ChildItem -Path $NgcPath -Force -ErrorAction SilentlyContinue
if ($items.Count -eq 0) {
    Write-Host "NGC-Ordner ist leer. Kein aktiver PIN vorhanden." -ForegroundColor Yellow
    exit
}

Write-Host "Windows Hello Daten gefunden. Starte Bereinigung..." -ForegroundColor Green

# --- Dienste stoppen (optional, aber stabiler) ---
Write-Host "Stoppe Dienst: NgcSvc (falls vorhanden)..." -ForegroundColor Gray
Get-Service -Name NgcSvc -ErrorAction SilentlyContinue | Where-Object {$_.Status -eq "Running"} | Stop-Service -Force

# --- Besitz übernehmen ---
Write-Host "Übernehme Besitz..." -ForegroundColor Gray
takeown /f $NgcPath /r /d y | Out-Null

# --- Rechte setzen ---
Write-Host "Setze Berechtigungen..." -ForegroundColor Gray
icacls $NgcPath /grant Administrators:F /t | Out-Null

# --- Inhalte löschen ---
Write-Host "Lösche Inhalte..." -ForegroundColor Gray
Remove-Item "$NgcPath\*" -Recurse -Force -ErrorAction SilentlyContinue

# --- Kontrolle ---
$remaining = Get-ChildItem -Path $NgcPath -Force -ErrorAction SilentlyContinue
if ($remaining.Count -eq 0) {
    Write-Host "✔ Windows Hello (PIN) erfolgreich entfernt." -ForegroundColor Green
} else {
    Write-Host "⚠ Es sind noch Dateien vorhanden. Manuelle Prüfung nötig." -ForegroundColor Red
}

Write-Host "=== Fertig. Neustart empfohlen ===" -ForegroundColor Cyan



#informatik #informatik/PowerShell #informatik/Skripte #informatik/Windows
