File Search:
- Find all ADS files: `Get-Childitem -path C:\Users\CTF -force -recurse -ErrorAction 'silentlycontinue' | ForEach-Object {Get-Item $_.fullname -Stream * -ErrorAction 'silentlycontinue' | Where-Object {$_.stream -cnotmatch '.*DATA.*'} }`
