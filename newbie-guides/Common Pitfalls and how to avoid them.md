WIP


# pitfall #1: approaching linux like windows




# pitfall #2: windows VS linux filesystem differences



# pitfall #3: drivers



# pitfall #4: commands from the internet/AI



# pitfall #5: repositories


# pitfall #6: fractional scaling and games


# pitfall #7: NTFS



# pitfall #8: picking a desktop based on visual flair or "ricing"


# pitfall #9: Proton Versions



# pitfall #10: not having a bootable USB



# pitfall 11: backups, backups, backups.


# pitfall 12: linux on arm


Linux on ARM CPU's (like snapdragon) does exist, but is currently in a very bad state, to the point where you should ONLY use linux for arm on dev boards like the raspberry pi or if you want to involve yourself in the improvement of linux for arm. 

Due to how ARM currently works and a lack of standardization for the *device tree*, in order to support a device, the distribution has to explicitly build in support for that device's device tree. This basically means that a device being supported relies on at least one of these:

- the device uses the generic device tree (rare)
- the device's device tree is published by the manufacturer (also rare)
- someone went through the insane amount of effort it takes to reverse-engineer the device tree (as you can imagine, very rare)

Recently, microsoft has announced they'll be introducing a standard for this, in part because of Nvidia's RTX Spark announcement. Things will get better, but it will take time. 
