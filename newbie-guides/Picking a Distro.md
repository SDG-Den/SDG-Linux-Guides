Very frequently, when a new or aspiring Linux user asks "what distribution do i use?", they are met with a bunch of people telling them "use <distro i'm using>, it's __the best one__".

This isn't always the case and can lead to someone trying a distro that doesn't match the experience they're looking for, potentially cutting this person's Linux journey short.

So instead, here's a guide for new users to pick their Linux distribution themselves. This should be applicable to basically all new users with limited prior experience. This guide does not apply to enthusiasts, developers and general tech nerds.

# What is a distro?

Linux itself is just a kernel. In order to get a fully functional system, you need a bunch of other components around that kernel. For every component, there's various options, which you get to pick from.

Obviously, picking each component yourself would be an extremely tedious process that not many people would want to go through. Imagine wanting to buy a car and finding out you have to buy the engine block and then buy every other component separately, putting it together yourself.

This is what distributions are for. Distributions are a pre-made selection of components that provides you with a functional system of some type.

Different distributions contain different sets of components, and may be aimed at different use-cases (for example, Ubuntu server doesn't have a desktop environment at all, because it's meant for server use.)

For daily use, you'll want to get a *desktop* distro.

# Tier 1 vs tier 2 distro's

There are different "tiers" of distro's, this is generally used to talk about the distro's relation to other distro's. A tier 2 distro is based on a tier 1 distro, a tier 3 distro is based on a tier 2 distro etc. The "tier" of the distribution says nothing about how good a distribution is.

This can also be used to categorize distro's into "families". for example, the following are all based on arch:
* EndeavourOS
* CachyOS
* Garuda Linux
* steamOS 
  
This makes them all Tier 2 distro's in the Arch family. 

# The big three families

Broadly, most popular linux distributions fall within one of three families, being based on one of three different distribution families. For new users, i'd highly recommend picking something from the big three simply because you'll find significantly more community support and resources when you need help.

the three families are:

- Fedora
- Arch Linux
- Debian/Ubuntu

Debian/Ubuntu is a bit special, as Ubuntu is a tier 2 distro based on Debian but because most popular distro's in this family are based on Ubuntu rather than Debian directly, some people effectively count Ubuntu as a tier 1 distro with its derivations being tier 2. Hence why they're mentioned together. Technically all children of Ubuntu are also just Debian family.

# What components you should actually care about

Out of all of those components you need, most of them __don't really matter__ for a new user. You can trust that any desktop distro will come with all the needed core components, and whether you're using for example ufw or firewalld as your firewall doesn't really matter, as long as you have a firewall.

The two componetns that do matter are:

- Software Installation
- Desktop Environment

# Software installation

Software installation is a bit of an umbrella term here, because it's not just about __how__ you install software, but also what software is available and what versions.

This is generally split by family, as all distributions in the same family use the same package manager and are generally able to use repositories (collections of software available through your package manager) from any distro in that family.

- Ubuntu/Debian - these distro's generally favor stability, having a smaller list of available software by default and with slightly out-of-date versions, but the available software is rock-solid stable.

- Arch Linux - these distro's favor getting the latest and greatest, you get updates for software basically immediately and have access to the largest amount of software, but you may end up being the test driver for some of it.

- Fedora - the middle ground. Fedora releases updates a bit slower than Arch, verifying stability first, but still a lot faster than Ubuntu/Debian. Weeks instead of months. Fedora does have less available software than arch, focusing on more mature projects.

Pick one of these three, then move on to the next section.

Do note, this is about what you'll find in these distributions *at base*, you can of course add repositories that give you more up-to-date software on Debian, or go the other way around switching to an "LTS" repository on Arch. these have to be done manually afterwards and thus, it is better to pick a distro family that defaults to what you want.  

# Desktop environment

Your desktop environment consists of basically everything you interact with. on Windows, this consists of your desktop, your bar, your settings menus, things like your start menu and runner, and generally it'll also come bundled with your file explorer and various other parts you'd consider "part of the operating system" rather than "preinstalled software" on windows. Some desktops may not have all the same components as windows because they may work differently, for example, GNOME has a top status bar rather than a taskbar.

You can get __any__ of these desktops on __any__ of the big 3 families.

Your desktop environment will determine basically 95% of your experience, as such, i actually recommend picking and trying a couple.

Here's some recommendations for popular desktops:

- KDE plasma - windows-like by default with high customizability
- GNOME - android/mac style desktop
- cinnamon - windows 7-like
- XFCE - lightweight and simple
- cosmic - gnome-like desktop with auto-tiling

pick at least 3 to try.

# Trying distro's

Trying a distro is actually very easy and recommended! Many distributions come with a __live environment__ for the installer, that means the installation software runs within a full version of the desktop, so you can try the desktop before you install it as well as verify that this distribution works correctly with your hardware.

The best way to do this is to make a USB stick into a ventoy. This allows you to then place ISO files on the USB stick, boot from the USB stick and select the ISO file to use, no flashing needed.

An easy way to try out various desktops is to use the Fedora iso's for them, as they are each a separate iso file. CachyOS also offers all of the above desktops, but since CachyOS has a single iso and you select your DE during installation, you can only try the KDE plasma environment before installing.

You can find the Fedora spins here: [https://fedoraproject.org/spins/](https://fedoraproject.org/spins/)  
You can find Fedora KDE here: [https://fedoraproject.org/kde/](https://fedoraproject.org/kde/)  
You can find Fedora with GNOME here: [https://fedoraproject.org/workstation/](https://fedoraproject.org/workstation/)

For Ubuntu/Debian based distro's:  
Ubuntu flavours can be found here: [https://ubuntu.com/desktop/flavors](https://ubuntu.com/desktop/flavors)  
Linux min can be found here: [https://linuxmint.com/download.php](https://linuxmint.com/download.php)

for Arch based distro's:  
CachyOS list of desktop environments: [https://wiki.cachyos.org/installation/desktop_environments/](https://wiki.cachyos.org/installation/desktop_environments/)

When trying the distro, make sure to do the following:

- check if your wifi, bluetooth, audio and camera are working
- Check if the distro has the other features you want (like a GUI app store to install software from)
- Check that configuring the distro is as easy as you would want it to be.
- Check that the distro runs well on your device
- Check that you like the defaults, or that you can tweak the settings of the desktop to something you like.

# Installing

Once you've picked your desktop and which family of distro's you want to use, use the above resources to find a distro from that family with the desired desktop.

{lace the ISO on your ventoy and follow the install instructions. Make sure to select the correct desktop if your distro of choice offers multiple during installation (like CachyOS).

# What if i cannot pick or change my mind?

If you change your mind on the distro family, you'll have to reinstall sadly.

However, if you change your mind on the desktop environment, you can always install a different one. You can even have multiple and pick between them!

# Hey, i want to run x software, i need a distro that can do that

Generally, running specific pieces of software isn't really down to the distro, especially if you're intending to carry software over from windows.

The rule of thumb is that if the software has some kind of DRM protection system, anti-piracy system or kernel-level anti-cheat system, it simply will not run on Linux.

If you can, find an alternative to the software. If the software itself is vital, then you simply cannot switch to Linux.

# What about gaming? i heard x distro was good for gaming

It __really__ doesn't matter that much. Some distro's come pre-optimized for gaming (like Bazzite and CachyOS) but truth is those optimizations aren't __that__ big of a deal and you shouldn't pick your distro based on that.

As for games and which ones run, generally, it either runs on Linux or it doesn't. You may need a specific proton version or be running under a specific display server, but there isn't really a situation where a game will run on Fedora but cannot be made to run on Ubuntu.

For gaming in general, the best way to approach Linux is the way you'd approach a console. "I have this console, so i have access to play these games". You're not on the "PC" platform together with windows users, you're on the "Linux" platform while they're on the "Windows" platform, and Windows does have __a lot__ of exclusives.

For resources on this, check protondb and AreWeAnticheatYet. ProtonDB is a good overview of how well a game runs on Linux and AreWeAnticheatYet follows Linux compatibility for bigger multiplayer games that have some form of anticheat.

# What about NVIDIA support?

NVIDIA support isn't as bad as it was 10 years ago, so most distro's will work fine with modern NVIDIA cards. if you pick any distro within the big three families that __isn't__ abandoned, you should at most have to run a single command to install the drivers for your GPU.

# So what do you run?

In case anyone wants to know: I run CachyOS with MangoWM and DankMaterialShell on my main rig, Void Linux with the same setup on my laptop and Ubuntu server on my servers. My exact configuration is not stock and cannot be installed from any ISO, but a similar setup can be found in the CachyOS installer as their MangoWM option includes DankMaterialShell. 

