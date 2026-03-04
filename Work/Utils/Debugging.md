## Heap corruption detection
Run console as admin.
```PowerShell
cd "c:\Program Files (x86)\Windows Kits\10\Debuggers\x64"  
.\gflags.exe /p /enable iolitelx.exe /full  
.\gflags.exe /p /disable iolitelx.exe /full  
```
