## Find a file by filename
```
find / -name "*filename*" 2>/dev/null
```

## Find a file by contents
```
find / -type f -exec grep "searchtext" {} 2>/dev/null \;
```

## Boot and Drive Editing

- `lsblk` list blocks
- `xxd` gives a hexdump of the drive, I.E: `sudo xxd -l 512 -g 1 /dev/vda` gets a hexdump of the first 512 Bytes of /dev/vda 
