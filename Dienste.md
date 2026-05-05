```
$services = Get-CimInstance Win32_Service | ForEach-Object {  
[PSCustomObject]@{  
Type = "Service"  
Name = $_.Name  
Path = ""  
Account = $_.StartName  
State = $_.State  
Source = "ServiceControlManager"  
}  
}
```

#informatik #informatik/PowerShell #informatik/Konsole 