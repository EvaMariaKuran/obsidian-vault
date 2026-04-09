Get-WmiObject Win32_Service |
Where-Object {
	$_.StartName -notlike "NT AUTHORITY*" -and
	$_.StartName -ne "LocalSystem"
} |
Select-Object Name, DisplayName, StartName, State |
Sort-Object StartName |
Format-Table -AutoSize

Get-WmiObject Win32_Service |
		Select-Object Name, DisplayName, StartName, State |
	Sort-Object StartName |
	Format-Table -AutoSize




Get-ScheduledTask | 
Select-Object TaskName, @{Name="RunAsUser";Expression={$_.Principal.UserId}}, State, TaskPath | 
Sort-Object RunAsUser, TaskName | 
Format-Table -AutoSize
