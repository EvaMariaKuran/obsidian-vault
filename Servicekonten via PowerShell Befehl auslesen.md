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



# --- TASKS über COM (vollständig, auch "unsichtbare") ---
$service = New-Object -ComObject "Schedule.Service"
$service.Connect()

function Get-AllTasks {
    param($folder)

    $result = @()

    foreach ($task in $folder.GetTasks(0)) {
        $result += [PSCustomObject]@{
            Type        = "Task"
            Name        = $task.Name
            Path        = $folder.Path
            Account     = $task.Definition.Principal.UserId
            State       = $task.State
            Source      = "TaskScheduler"
        }
    }

    foreach ($subFolder in $folder.GetFolders(0)) {
        $result += Get-AllTasks -folder $subFolder
    }

    return $result
}

$tasks = Get-AllTasks -folder $service.GetFolder("\")

# --- DIENSTE ---
$services = Get-CimInstance Win32_Service | ForEach-Object {
    [PSCustomObject]@{
        Type        = "Service"
        Name        = $_.Name
        Path        = ""
        Account     = $_.StartName
        State       = $_.State
        Source      = "ServiceControlManager"
    }
}

# --- KOMBINIEREN ---
$all = $tasks + $services

# --- OPTIONAL: Standardkonten ausblenden ---
$filtered = $all | Where-Object {
    $_.Account -and
    $_.Account -notmatch "SYSTEM|LOCAL SERVICE|NETWORK SERVICE"
}

# --- AUSGABE ---
$filtered |
Sort-Object Account, Type, Name |
Format-Table Type, Name, Path, Account, State -AutoSize

#informatik #informatik/PowerShell #informatik/Skripte 