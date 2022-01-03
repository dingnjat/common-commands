1. Edit `/etc/default/grub`
2. Change value `GRUB_DEFAULT=0` to 
```
GRUB_DEFAULT=saved
GRUB_SAVEDEFAULT=true
```
3. Run `sudo update-grub`
