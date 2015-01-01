# OVERVIEW

Based on OS X and Windows in internal SSD (Drive) and Ubuntu on external SSD (Drive)

create back up images of the OS X and Windows partition (optional but strongly recommended)
create a bootable USB stick with the ubuntu installer
holding down the option key, boot from the ubuntu installer stick
install ubuntu to the external hard disk
On reboot (I had to force the shutdown by pressing and holding the power button, as it seemed to have stalled some time after clicking reboot), hold down the option key to boot into OS X
download and install Refind boot manager
edit the refind configuration file /efi/refind/refind.conf (the line you're looking for starts with scanfor) and make sure hdbios is included in the list
on reboot, you should now be greeted with a menu containing a ubuntu, Mac and Windows logo (you can press esc to refresh the list, as external drives can take some time to show up; you can configure refind to pause befaure showing hte menu)

Ignore the Windows part if we don’t care about creating a dual boot OS X and Windows on the internal SSD.
