# 3 - THE WINDOWS OPERATING SYSTEM
## 3.1 Windows History
The first computers didn't have modern storage devices such as SD Card / Hard Drive / USB ... The modern storage require software to read from,write to and to manage the data that they store.
This where The Disk Operating System (DOS) wich i do it's magic, well there is no magic ofc  ;) , after that  Microsoft bought DOS and developed MS-DOS. Which use a commands line that people can manage data from it, create programs ...
## 3.2 Windows Architecture and Operations
### Hardware Abstraction Layer
 
A hardware abstraction layer (HAL) is software that handles all of the communication between the hardware and the kernel.
kernel is the core of the operating system and has control over the entire computer.
In some instances, the kernel still communicates with the hardware directly, so it is not completely independent of the HAL. The HAL also needs the kernel to perform some functions.
### User Mode and Kernel Mode
There are two different modes in which a CPU operates when the computer has Windows installed: the user mode and the kernel mode.
* Installed applications run in user mode
Programs such as user applications, run in user mode and have no direct access to hardware or memory locations.
* Operating system code runs in kernel mode
Code that is executing in kernel mode has unrestricted access to the underlying hardware and it's mostly reserved for the most trusted functions of the OS, crashes in code running in kernel mode stop the operation of the entire computer.
### Windows BooT Process
* Boot Sequence for Windows:
* Power on Self Test (***POST***)
* POST for each adapter card, to make sure all of the hardware devices are communicating.
* ***BIOS*** reads the MBR, the MBR contains a small program that is responsible for locating and loading the operating system.
* ***UEFI*** firmware boots by loading EFI program files, stored as .efi files in a special disk partition, known as the EFI System Partition (ESP).
* ***MBR*** takes over control of the boot process and starts BOOTMGR
* ***BOOTMGR*** switches the system from real mode to protected mode so that all of the system memory can be used
* ***BOOTMGR*** reads the Boot Configuration Data file to know which OS to load and where to find the OS on the boot partition
* ***BCD*** contains any code needed to start the computer, along with an indication of whether it's coming out of ***Hebirnation***, or a ***cold start*** 
* ***BOOTMGR*** invokes ***WINLOAD.EXE***, To read the ***Hiberfil.sys*** file which contains the ***State*** of the computer when it was put into hibernation.
* ***Winload.exe*** also uses Kernel Mode Code Signing (KMCS) to make sure that all drivers are digitally signed.
* ***Winload.exe*** reads the registry files and loads device drivers
* ***Winload.exe*** runs ***Ntoskrnl.exe*** which starts the Windows kernel and sets up the ***HAL***.
* ***NTOSKRNL.EXE*** starts the ***WINLOGON*** service and displays the Windows ***login*** screen

### Windows File System
* FAT

This is a simple file system supported by many different operating systems.
FAT has limitations to the number of partitions, partition sizes, and file sizes that it can address, so it is not usually used for hard drives (HDs) or solid-state drives (SSDs) anymore.
Both FAT16 and FAT32 are available to use, with FAT32 being the most common because it has many fewer restrictions than FAT16.

* NTFS

This is the most commonly used file system when installing Windows. All versions of Windows and Linux support NTFS.
Mac-OS X computers can only read an NTFS partition. They are able to write to an NTFS partition after installing special drivers.
NTFS formatting creates important structures on the disk for file storage, and tables for recording the locations of files:

Partition Boot Sector
```bash
This is the first 16 sectors of the drive. It contains the location of the Master File Table (MFT). The last 16 sectors contain a copy of the boot sector.
```
Master File Table (MFT)
```bash
This table contains the locations of all the files and directories on the partition, including file attributes such as security information and timestamps.
```
System Files
```bash
These are hidden files that store information about other volumes and file attributes.
```
File Area
```bash
The main area of the partition where files and directories are stored.
```
### Windows Registry
Windows stores all of the information about hardware, applications, users, and system settings in a large database known as the registry.
3.2.10
The Windows Registry
Windows stores all of the information about hardware, applications, users, and system settings in a large database known as the registry.
The registry is a hierarchical database where the highest level is known as a hive, below that there are keys, followed by subkeys.

The table lists the five hives of the Windows registry:
* ***HKEY_CURRENT_USER (HKCU)*** - Info about the currently logged in user.
* ***HKEY_USERS (HKU)*** - Info about all the user accounts
* ***HKEY_CLASSES_ROOT (HKCR)*** - information about OLE <= allows users to embed objects from other applications into a single document .
* ***HKEY_LOCAL_MACHINE (HKLM)*** - Holds system-related information
* ***HKEY_CURRENT_CONFIG (HKCC)*** - Info about the current hardware profile.

Registry keys can contain either a subkey or a value. The different values that keys can contain are as follows:

* ***REG_BINARY*** - Numbers or Boolean values
* ***REG_DWORD*** - Numbers greater than 32 bits or raw data
* ***REG_SZ*** - String values
