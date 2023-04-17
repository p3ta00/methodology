# Enumerate interfaces
```
ipconfig /all
```
```
arp-a
```
```
route print
```
```
netstat -ano
```
# Enumerate Protection
```
Get-MpComputerStatus
```
```
Get-AppLockerPolicy -Effective | select -ExpandProperty RuleCollections
```
```
Get-AppLockerPolicy -Local | Test-AppLockerPolicy -path C:\Windows\System32\cmd.exe -User Everyone
```
# Initial Enumeration
```
tasklist /svc
```
Send the list to ChatGBT as ask it to filter third-party applications
```
set
```
run this in cmd
```
systeminfo
```
### View Hotfixes/patches
```
wmic qce
```
```
Get-HotFix | ft -AutoSize
```
## View installed programs
### CMD

```
wmic product get name
```
### Powershell
```
Get-WmiObject -Class Win32_Product |  select Name, Version
```
Run LaZagne to check if stored credentials for those applications are installed. Also, some programs may be installed and running as a service that is vulnerable.

# Users and Groups
```
query user
```
```
echo %USERNAME%
```
```
whoami /priv
```
```
whoami /groups
```
```
net user
```
```
net localgroup
```
```
net localgroup "administrators"
```
```
net 
```
# Enumerating Network Services
## Listing Named Pipes with Pipelist
### Powershell
```
gci \\.\pipe\
```
### CMD
```
pipelist.exe /accepteula
```
### Reviewing LSASS Named Pipe Permissions
```
accesschk64.exe /accepteula \\.\Pipe\lsass -v
```
### Checking WindscribeService Named Pipe Permissions
```
accesschk64.exe -w \pipe\* -v
```
```
accesschk64.exe -accepteula -w \pipe\WindscribeService -v
```
