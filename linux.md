## Find a file by filename
```
find / -name "*syslog*" 2>/dev/null
```

## Find a file by contents
```
find / 2>/dev/null -exec grep "searchtext" {}
```

