Get-ScheduledTask | 
Select-Object TaskName, @{Name="RunAsUser";Expression={$_.Principal.UserId}}, State, TaskPath | 
Sort-Object RunAsUser, TaskName | 
Format-Table -AutoSize

#informatik #informatik/PowerShell 