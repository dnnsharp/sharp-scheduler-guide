# Examples

1. Delete files older than one month (31 days) from a given folder

We create a new job in the Jobs administrative page. A trigger is needed to schedule this job and for this maintenance task, a monthly frequency seems often enough, so we add a "Repeat on interval" trigger with the interval set to 14 days. Twice a month we will delete the files that are older than a month. Now we need some actions to get the job done. We will use a PowerShell script since it is the more generic (the folder is not necessary related to DNN) and a powerful (we can use the .NET functionality) method, but other methods are also possible (some custom executable or defined method). So we add a "Run PowerShell Script" action with the following script:

function RemoveFiles($path = $pwd) 
{ 
    [hashtable]$Return = @{} 
    $Return.files = 0
    
    foreach ($item in Get-ChildItem $path) {
        if (Test-Path $item.FullName -PathType Container) {
            $filesIn = RemoveFiles $item.FullName
            $Return.files += $filesIn.files
        } 
        else { 
            $limit = (Get-Date).AddDays(-31)
            if ($item.LastWriteTime -lt $limit) {
                 Remove-Item $item.FullName
            }
            else {
                $Return.files += 1
            }
        }
    }
     
    # also remove empty folders
    if ($Return.files -eq 0) {
        #Here the -force option will delete hidden and system files.
        #recurse needed to avoid confirmation dialog
        Remove-Item $path -force -recurse
    }
        
    return $Return
}
RemoveFiles("C:\Logs")

This script will remove recursively the files older than 31 days from the folder "C:\Logs" (change it to your location), including the folders left empty. Being run from the IIS service, if not inside the host folder, be sure you have the appropriate rights for the application, that is "full control" for the "Network Service" user. 
WARNING Also, please be sure you know what you are doing, the script will really delete those files!