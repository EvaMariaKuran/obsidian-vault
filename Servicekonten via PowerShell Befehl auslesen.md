Get-WmiObject Win32_Service |
Where-Object {
	$_.StartName -notlike "NT AUTHORITY*" -and
	$_.StartName -ne "LocalSystem"
} |
Select-Object Name, DisplayName, StartName, State |
Sort-Object StartName |
Format-Table -AutoSize



Alle Servicekonten: 

Get-WmiObject Win32_Service |
		Select-Object Name, DisplayName, StartName, State |
	Sort-Object StartName |
	Format-Table -AutoSize
