# VirtualXP

Virtual Machine running in a Web browser.

![alt screenshot](https://raw.githubusercontent.com/lrusso/VirtualXP/master/VirtualXP.png)

## Web

https://lrusso.github.io/VirtualXP/VirtualXP.htm

## Editing the VirtualXP Registry

Within the **VirtualXP.iso** image file, there is a Registry file **\I386\SYSTEM32\CONFIG\DEFAULT** that you must copy to your hard drive (your hard drive must have a standard Windows installation) and run from that standard Windows installation the following line:

```
reg load HKLM\OFFLINE C:\DEFAULT
```

This will mount the VirtualXP Registry to **HKEY_LOCAL_MACHINE\OFFLINE**. Now open the Registry editor and at the mentioned location you will find all the settings that VirtualXP is using. Modify all the things that you may need in there and after that run the following line:

```
reg unload HKLM\OFFLINE
```

This will remove the **HKEY_LOCAL_MACHINE\OFFLINE** Registry folder, unmount the **DEFAULT** file and will save the changes in the file. After this, you must copy the modified **DEFAULT** file to the VirtualXP image file at **\I386\SYSTEM32\CONFIG\DEFAULT**.

## The MODELRAM.EXE file

Within the **VirtualXP.iso** image you will find the **\MODELRAM.EXE** file that it is self extracting exe file created with the 7-Zip command line that automatically extracts the **Documents and Settings** folder in the RAMDisk when VirtualXP is booting. The command to create this file is the following:

```
7z a MODELRAM.EXE -mx9 -sfx "Documents and Settings"
```

## The VirtualXP emulator is a modified version of Halfix

https://github.com/nepx/halfix
