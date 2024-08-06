# File Search:



## Search by Attribute
- Find all Files with an ADS:
```
Get-Childitem -path C:\Users\CTF -force -recurse -ErrorAction 'silentlycontinue' | ForEach-Object {Get-Item $_.fullname -Stream * | Where-Object {$_.stream -cnotmatch '.*DATA.*'} } 2>$null
```
- Find all hidden files
```
Get-Childitem -Path C:\Users\CTF -Force -Recurse 2>$null
```

## Search by String
- Search by Filename
```
Get-Childitem -Path C:\Users\CTF -Force -Recurse -Include '*key*' 2>$null
```
- Search by contents
```
Get-Childitem -Path 
```

# Registry Search

## Common Registries

Persistence
- `HKLM`
  - `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run`
  - `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\RunOnce`
- `HKCU`
  - `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`
  - `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce`
