WIP

In this guide, we'll go over how to install and manage software on Linux!

Installing software is done through what is called a package manager, and a piece of software is called a package. A package may have dependencies, other packages it needs to work correctly. Your package manager automatically handles these dependencies. Unlike in windows, software isn't monolithic, meaning that the program doesn't come with all of its own dependencies inside, this saves space as multiple programs can for example use the same libraries. A lot of Linux software is split into many parts through these dependencies.  


# what is a package manager

A package manager is generally a terminal-based tool that allows you to install, uninstall and update packages, automatically including their dependencies. To do this, your package manager uses what are called "repositories" or "repos" for short. 

Your desktop distribution will come with a default configured repository, which you should stick to until you are more familiar with Linux.


# different package managers by platform

### Arch:

Arch uses pacman. pacman uses shorthand flags such as -U for upgrade, -S for sync (install) and -R for remove, these can have options which are simply added afterwards

for example:
sudo pacman -Syu lolcat

this command will sync your package database, upgrade all software to latest and install the program "lolcat"

Arch also has the Arch User Repository (AUR).

the AUR is kind of a testing ground. It is for *user-packaged software*, and there is no verification of the software. When software gets enough votes on the AUR, it gets a pacman release in the default "extra" repositories. 

Software from the AUR should be approached as effectively untested, and it is up to you whether or not to trust the dev and the software. 

You can also find -git versions of packages that do exist in the pacman repositories in the AUR, these should be treated effectively as "beta" branches, this generally *directly* gives you the latest github version. This *can* be great for early-adopters who want to keep up with the development of the software, but comes with a lot of risk. 


### ubuntu and debian:

Ubuntu and Debian both use APT, which uses full subcommands such as install, update and upgrade. 

for example:
sudo apt update && sudo apt upgrade -y

this command is actually two commands, the first updates your package database, the second updates all your installed software.

ubuntu and debian also have dpkg, which is a tool to handle .deb files.

these are used for a more manual install, which can be useful. Do keep in mind, dpkg doesn't install dependencies. Best used for standalone binaries or as a last resort.  


# graphical installers




# installing via the terminal




# updating your system




# removing software


