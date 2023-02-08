# 3 - THE WINDOWS OPERATING SYSTEM
## 3.1 Windows History
The first computers didn't have modern storage devices such as SD Card / Hard Drive / USB ... The modern storage require software to read from,write to and to manage the data that they store.
This where The Disk Operating System (DOS) wich i do it's magic, well there is no magic ofc  ;) , after that  Microsoft bought DOS and developed MS-DOS. Which use a commands line that people can manage data from it, create programs ...
## 3.2 Windows Architecture and Operations
### + Hardware Abstraction Layer
 
A hardware abstraction layer (HAL) is software that handles all of the communication between the hardware and the kernel.
kernel is the core of the operating system and has control over the entire computer.
In some instances, the kernel still communicates with the hardware directly, so it is not completely independent of the HAL. The HAL also needs the kernel to perform some functions.
### + User Mode and Kernel Mode
There are two different modes in which a CPU operates when the computer has Windows installed: the user mode and the kernel mode.
* Installed applications run in user mode
Programs such as user applications, run in user mode and have no direct access to hardware or memory locations.
* Operating system code runs in kernel mode
Code that is executing in kernel mode has unrestricted access to the underlying hardware and it's mostly reserved for the most trusted functions of the OS, crashes in code running in kernel mode stop the operation of the entire computer.
### + Windows BooT Process
* Start with Power on Self Test (***POST***)
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
* Finally ***NTOSKRNL.EXE*** starts the ***WINLOGON*** service and displays the Windows ***login*** screen

### + Windows File System
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
### + Windows Registry
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

Potentially malicious applications can add registry keys so that they start when the computer is started. During a normal boot, the user will not see the program start because the entry is in the registry and the application displays no windows or indication of starting when the computer boots

When performing normal security audits, or remediating an infected system, review the application startup locations within the registry to ensure that each item is known and safe to run.

The registry also contains the activity that a user performs during normal day-to-day computer use. This includes the history of hardware devices, including all devices that have been connected to the computer including the name, manufacturer and serial number. Other information, such as what documents a user and program have opened, where they are located, and when they were accessed is stored in the registry. This is all very useful information when a forensics investigation needs to be performed.

## 3.3 Windows Configuration and Monitoring
### + CLI and PowerShell
The Windows command line interface (CLI) can be used to run programs, navigate the file system, and manage files and folders.
The Windows PowerShell, is an integrated program within Windows that can be used to create scripts to automate tasks that the regular CLI is unable to create.
These are the types of commands that PowerShell can execute:
* ***cmdlets*** - These commands perform an action and return an output or object to the next command that will be executed.
* ***PowerShell scripts*** - These are files with a ***.ps1*** extension that contain PowerShell commands that are executed.
* ***PowerShell functions*** - These are pieces of code that can be referenced in a script.

### + The NET command 
One important command is the net command, which is used in the administration and maintenance of the OS.
The table lists some common net commands:
* ***net accounts*** - Sets password and logon requirements for users
* ***net session*** - Lists or disconnects sessions between a computer and other computers on the network
* ***net share*** - Creates, removes, or manages shared resources
* ***net start*** - Starts a network service or lists running network services
* ***net stop*** - Stops a network service
* ***net use*** - Connects, disconnects, and displays information about shared network resources
* ***net view*** - Shows a list of computers and network devices on the network

### + Windows Server
These are some of the services that Windows Server provides:
* ***Network Services*** - DNS, DHCP, Terminal services, Network Controller, and Hyper-V Network virtualization
* ***File Services*** - SMB, NFS, and DFS
* ***Web Services*** - FTP, HTTP, and HTTPS
* ***Management*** - Group policy and Active Directory domain services control

## 3.4 Windows Security
### + The netstat Command
When malware is present in a computer, it will often open communication ports on the host to send and receive data.
The netstat command can be used to look for inbound or outbound connections that are not authorized. (***Netstat -abno***)
When a program is suspected of being malware, a little research can be performed to determine its legitimacy. From there, the process can be shut down with Task Manager, and malware removal software can be used to clean the computer.
### + Event Viewer
Windows Event Viewer logs the history of application, security, and system events.
Windows includes two categories of event logs: Windows Logs, and Application and Services Logs.  Events that are displayed in these logs have a level: information, warning, error, or critical.
It is also possible to create a custom view. This is useful when looking for certain types of events, finding events that happened during a certain time period, displaying events of a certain level, and many other criteria.
### + Local Security Policy
A security policy is a set of objectives that ensures the security of a network, the data, and the computer systems in an organization.
Password guidelines - Any user that must log on to a computer or connect to a network resource should be required to have a password.
The Account Lockout Policy - in Account Policies to prevent brute-force login attempts.
The Local Security Policy applet contains many other security settings that apply specifically to the local computer. You can configure User Rights, Firewall Rules, and even the ability to restrict the files that users or groups are allowed to run with the AppLocker.
