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

## STEP 1

OS X SAT SMART Driver
#####################

This is a kernel driver for Mac OS X external USB or FireWire drives.
It extends the standard driver behaviour by providing access to drive
SMART data. The interface to SMART data is same as with ATA family
driver, so most existing applications should work. The driver requires
a SAT (SCSI ATA Translation) capable external drive enclosure.

The driver consists of a kernel extension and a user client interface
library.

The code is based on Apple opensource files and is therefore published
under Apple Public Source License. For details see
http://www.opensource.apple.com/license/apsl/

Install
=======

 * Use the dmg image and the installer
 * Power cycle the external drives
 * Check DiskUtility. The disk should have "S.M.A.R.T. Status: Verified"


Uninstall
=========

 * Remove driver and plugin
    sudo rm -r /System/Library/Extensions/SATSMARTDriver.kext
    sudo rm -r /System/Library/Extensions/SATSMARTLib.plugin
 * Reboot

## STEP 2

http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-mac-osx

## STEP 3: Actually Install Ubuntu into our external Drive

Reboot and hold the OPTION key.

Reference - http://askubuntu.com/questions/604193/i8042-error-on-macbook-7-1
For MacBookPro5,2 (2009 17”), we will get an error that says "8042: No controller found."
The solution is simple to edit our grub command by hitting “e” and append "nomodeset" in front of "quiet".

Once our Ubuntu LiveCD boots up, we can install it to our external disk by choosing the correct disk in the Installation Wizard.

## STEP 4: Download and Install Refind Boot Manager

http://www.rodsbooks.com/refind/yosemite.html
http://www.rodsbooks.com/refind/installing.html#nolinux

http://sourceforge.net/projects/refind/  (I used 0.8.7 as of 21st June 2015)
