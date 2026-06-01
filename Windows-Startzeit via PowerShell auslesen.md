Get-WinEvent -ProviderName Microsoft-Windows-Diagnostics-Performance |
  Where-Object { $_.Id -eq 100 } |
  Select-Object TimeCreated, Message |
  Format-List


#informatik #informatik/PowerShell #informatik/Windows 
