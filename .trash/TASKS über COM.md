(vollständig, auch "unsichtbare")


```
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

