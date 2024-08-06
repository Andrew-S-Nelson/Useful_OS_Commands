# File Search:
- Find all Files with an ADS:
```
Get-Childitem -path C:\Users\CTF -force -recurse -ErrorAction 'silentlycontinue' | ForEach-Object {Get-Item $_.fullname -Stream * | Where-Object {$_.stream -cnotmatch '.*DATA.*'} } 2>$null
```
- Find all hidden files
```
Get-Childitem -Path C:\Users\CTF -Force -Recurse 2>$null
```
- Search by Filename
```
Get-Chilitem -Path C:\Users\CTF -Force -Recurse -Include '*key*' 2>$null
```
