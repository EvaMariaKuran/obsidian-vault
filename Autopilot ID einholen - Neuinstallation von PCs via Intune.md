1. Land, Sprache + Tastaturlayout bestätigen 
2. Updates suchen + aktualisieren + neustarten
3. Shift + F10 drücken 
4. Befehl: powershell.ee
5. Befehl: 
```
> [[Net.ServicePointManager]]::SecurityProtocol = [[Net.SecurityProtocolType]]::Tls12
>  Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned
>  Install-Script -Name Get-WindowsAutopilotInfo -Force
>  Get-WindowsAutopilotInfo -Online
```

6. Adminanmeldung (Intune Administrator)

test zurück - yeyyyy it is working :)


#informatik #informatik/PowerShell #Microsoft365 #informatik/Windows #informatik/Skripte 