@echo off
setlocal enabledelayedexpansion

set "FOLDER=%~dp0"
set "COUNTER=1"

echo Folgende Dateien werden umbenannt (sortiert nach Datum):
echo =========================================================

for /f "delims=" %%F in ('dir /b /o:d "%FOLDER%*.drp" 2^>nul') do (
    if !COUNTER! LSS 10  set "NUM=00!COUNTER!"
    if !COUNTER! GEQ 10  set "NUM=0!COUNTER!"
    if !COUNTER! GEQ 100 set "NUM=!COUNTER!"

    echo [!COUNTER!] %%F  --^>  DRP!NUM!.drp
    set /a COUNTER+=1
)

echo.
set /p CONFIRM=Umbenennung durchfuehren? (J/N): 
if /i not "%CONFIRM%"=="J" (
    echo Abgebrochen.
    pause
    exit /b
)

set "COUNTER=1"
for /f "delims=" %%F in ('dir /b /o:d "%FOLDER%*.drp" 2^>nul') do (
    if !COUNTER! LSS 10  set "NUM=00!COUNTER!"
    if !COUNTER! GEQ 10  set "NUM=0!COUNTER!"
    if !COUNTER! GEQ 100 set "NUM=!COUNTER!"

    ren "%FOLDER%%%F" "DRP!NUM!.drp"
    set /a COUNTER+=1
)

echo.
echo Fertig! Alle Dateien wurden umbenannt.
pause



#informatik #informatik/Skripte #informatik/Batch-Datei