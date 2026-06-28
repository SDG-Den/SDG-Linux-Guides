WIP



# what is dual-booting

Dual-Booting is the practice of having multiple operating systems installed, and being able to pick which one to use when you start your device. 

You are not limited to two operating systems this way, in fact you *can* have as many as you want, this guide will only focus on using *two* operating systems.

Generally, the way this is set up is by *chain-loading* the bootloader for your other operating system(s) from your primary operating system (which will generally be a linux-based operating system, as windows' bootloader does not allow easy chainloading)

when you do this, on system boot, your system will load your primary bootloader, which will then display a menu that gives you the option to load into your primary OS or load into your secondary OS (or any other OS you have registered in your bootloader), which will trigger the chain-load, making your primary bootloader tell your device to load the bootloader for the selected OS. 

# dual-booting on one drive (linux+windows)

on a fresh drive with nothing installed, install windows *first*, windows has a tendency to *erase* your EFI boot partition when installing or updating the system. this will also prevent you from using limine as your bootloader because it is too big to fit on the EFI partition windows makes.

during the windows install, make sure to leave space on the disk for your linux install.

then, install linux, selecting the empty space to install to. it should automatically detect your EFI partition on the drive and add its bootloader (assuming there is space).

after this, reboot and make sure to select linux as your boot target in your bios.

on linux, you now want to add your windows install to your bootloader, most bootloaders have a scan command that automatically scans all connected drives to find operating systems.

make sure to take care of the following:
- do not enable bitlocker or any form of drive encryption on windows.
- do not use secureboot
- do not update windows unless you have a full backup of your boot partition. 

any of these 3 will likely break your linux install.

if you already have windows installed, you're going to have to shrink your windows drive. this generally will not work if you used bitlocker. if you did that, your only option is to *reinstall windows*. 

if you cannot shrink your drive from within windows using the proper windows tooling, *do not* try shrinking it externally using gparted or any other tool like it, this will likely prevent windows from working. again, if you cannot shrink your partition, your only option is to *reinstall windows*

once you have space on your drive, you can continue with the linux install. 

# dual-booting on one drive (linux+linux)




# dual-booting on two drives (linux+windows)




# dual-booting on two drives (linux+linux)




