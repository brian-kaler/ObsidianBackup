sudo cryptsetup --type tcrypt open /path/to/truecrypt-volume mapping-name

sudo mount -o uid=1001 /dev/mapper/mapping-name /media/tcv