1. Auto turn off screen
```
setterm --blank 1
```
And even better, if you want the command to be executed automatically at boot, you can add it to the GRUB commandline, to do so we have to edit the next file:

sudo nano /etc/default/grub
Once there, just add consoleblank=60 to GRUB_CMDLINE_DEFAULT, it should look like this:

GRUB_CMDLINE_LINUX_DEFAULT="quiet consoleblank=60"
Then close the file and save it, after that just run sudo update-grub and voila, every time you boot the screen will turn off automatically every 60 sec. (again, if idle).

And this way (adding the consoleblank to the GRUB) works even from remote terminals (ssh).
