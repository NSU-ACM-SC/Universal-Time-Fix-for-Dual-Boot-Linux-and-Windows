# Universal-Time-Fix-for-Dual-Boot-Linux-and-Windows

Noob people like me or others face some critical problem while using dual boot with Linux and Windows. One of the main problem is the universal time fixing.

While using dual boot, usually clock time gets reset once we change boot from linux to windows. This occurs mainly for bios clock reset for dual boot start. we can solve this problem easily by following any of the following steps.

1. Windows solution
2. Linux solution

It is better to follow the windows solution for this.

Windows Registry Editor Version 5.00
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation]
"RealTimeIsUniversal"=dword:00000001

Next, save that file as "WindowsTimeFix.reg" and exit Notepad. Then, navigate your file browser to wherever you saved the file we just made, and double click it. A box will pop up essentially asking if you want to proceed, tell it that you do.

Once that is done, you'll also want to disable Windows syncing the time. To do this, you'll want to go to your services application by clicking your start menu and typing "services.msc", and clicking "Services." Once there, scroll down until you find "Windows Time" and right click it, selecting "Properties." From here, you'll want to stop the process, and then disable it as well.

Or, run the command sc config w32time start= disabled from an elevated command prompt instead. To turn the Windows Time service back on at a later point in time, run the command sc config w32time start= auto instead.

Once Windows Time has been stopped and disabled and the registry key has been changed, your Windows will no longer have the time issue whenever you switch back and forth between GNU/Linux.


