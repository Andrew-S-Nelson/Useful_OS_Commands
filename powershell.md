# File Search:



## Search by Attribute
- Find all Files with an ADS:
```
Get-Childitem -path C:\Users\CTF -force -recurse -ErrorAction 'silentlycontinue' | ForEach-Object {Get-Item $_.fullname -Stream * | Where-Object {$_.stream -cnotmatch '.*DATA.*'} } 2>$null
```
- Find all hidden files
```
Get-Childitem -Path C:\Users\CTF -Recurse -hidden 2>$null
```

## Search by String
- Search by Filename
```
Get-Childitem -Path C:\Users\CTF -Force -Recurse -Include '*key*' 2>$null
```
- Search by contents
```
Get-Childitem -path C:\Users\CTF -force -recurse -ErrorAction 'silentlycontinue' | ForEach-Object {Get-Content $_.fullname | Where-Object {$_.stream -cmatch '.*SEARCH_KEY.*'} } 2>$null
```

# Registry Search

## Common Registries

Persistence
- `HKLM`
  - ```HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run```
  - `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\RunOnce`
- `HKCU`
  - `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`
  - `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce`

URL History
- `HKEY_CLASSES_ROOT\Local Settings\Software\Microsoft\Windows\CurrentVersion\AppContainer\Storage\microsoft.microsoftedge_8wekyb3d8bbwe\Children\001\Internet Explorer\DOMStorage`

USB History
- `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USB`
- `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR`

MRU (Most Recently Used) history
- `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePidlMRU`

Recent Files
- `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs`
