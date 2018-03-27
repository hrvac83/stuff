# HP ProBook 470 G3 WIN 10 bug fix

When you install a fresh copy of Windows 10 on this laptop you better have this file (or significant amount of tranquilizers).

## Problem

Disk usage is frequently higher than 95% although you have a fresh copy of windows and no workload on your machine. It causes system unresponsiveness, lag and few minor nervous breakdowns.

## Solution

The problem lies in a windows service called "Superfetch". To disable Superfetch you can perform the following steps.

### Disable from Services

1. Hold the Windows Key, while pressing “R” to bring up the Run dialog box.
2. Type “services.msc“, then press “Enter“.
3. The Services window displays. Find “Superfetch” in the list.
4. Right-click “Superfetch“, then select “Properties“.
5. Select the “Stop” button if you wish to stop the service. In the “Startup type” dropdown menu, choose “Disabled“.

### Disable from Registry

1. Hold the Windows Key, while pressing “R” to bring up the Run dialog box.
2. Type “Regedit“, then press “Enter“.
3. The Registry Editor window appears. Navigate to the following location in the Registry
    - HKEY_LOCAL_MACHINE
    - SYSTEM
    - CurrentControlSet
    - Control
    - Session Manager
    - MemoryManagement
    - PrefetchParameters
4. On the right side, double-click on “EnableSuperfetch“. If this value doesn’t exist, right-click the “PrefetchParameters” folder, then choose “New” > “DWORD Value“.
5. Give “EnableSuperfetch” value "0" to disable superfetch.
6. Select “OK“.
7. Close the Registry Editor.

### Important note

If you disable superfetch only in services, next windows update can enable it again so make sure you disable it from Registry too.

