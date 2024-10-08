# ethical-hacking
malware
# Malware Threats #

## Gain Access to the Target System using Trojans ##

### Gaining Control ###
#### yash ####
It can be found at: `Malware Threats\Trojans Types\Remote Access Trojans (RAT)\`.

``` njRAT v0.7d.exe ``` > Select port and start
  * Builder > Host:<Victim IP>, and select 'Copy to StartUp' and 'Registry StartUp' > 'Build' - Creates a 'Server.exe' file
  
In the victim machine: Copy the 'Server.exe' file to the Desktop and open it. It can access a victim's camera, log keystrokes, steal credentials stored in browsers, upload and download files, perform process and file manipulations, viewing the desktop...


### Obfuscating a Trojan ###
#### SwayzCryptor ####
It can be found at: `Malware Threats\Crypters\`.

``` swayzcryptor.exe ``` 
  * File -> The njRat 'Server.exe' created file
  * Select: Start Up, Mutex and Disable UAC
  * Encrypt (CryptedFile.exe)

In the victim machine: Copy the 'CryptedFile.exe' file to the Desktop and open it.


### Creating a Server ###
#### ProRat Tool ####
It can be found at: `Module 07 Malware Threats\Trojans Types\Remote Access Trojans (RAT)\`.

``` ProRat.exe ``` > 'Create ProRat Server (342 Kbayt)' > In 'General Settings' leave the default Settings but unselect all the ticks minus the ones in 'Invisibility' > Bind with File (Select an image)

In the victim machine: Run 'binded_server.exe'. It will turn into a .jpg.
In the attacker machine: Type the victim IP and port (default) and 'Connect'


### Creating a Trojan Server ###
#### Theef RAT Trojan ####
It can be found at: `Module 07 Malware Threats\Trojans Types\Remote Access Trojans (RAT)\`.

In the victim machine: ``` Server210.exe ```
In the attacker machine: ``` Client210.exe ``` > Type the victim IP and 'Connect' (leave the default ports)

#### GUI Trojan MoSucker ####
``` CreateServer.exe ``` > Default settings and save it as _'server.exe'_ and remember the port that was set
``` MoSucker.exe ``` > Type the IP of the victim and the port that was set in the previous step

In the victim machine, open ``` server.exe ```, and then on the attacker machine, in MoSucker click on 'Connect'.


### Creating and Remotely Controlling an HTTP Trojan ###
#### HTTP RAT ####
In one machine (the attacker): ``` httprat.exe ``` > Set the port to the desired one
In another machine (the victim): ``` httpserver.exe ``` - It will run on the background


- - - - 

## Infect the Target System using a Virus ##

### Creating a Virus ###
#### JPS Virus Maker Tool ####
It can be found at: `Module 07 Malware Threats\Virus Maker\`.

``` jps.exe ``` > Select the desired options, 'Restart', 'Rundll32', Select the Server name (Ex. 'Svchost.exe') > 'Create Virus!' - Other options appear, such as 'Enable Convert to Worm' > Enable it and call it, for instance, 'fedevi'

### Creating a Worm ###
#### Internet Worm Maker Thing ####
1. Name the worm, author, version, output path...
2. Select all the desired options
3. 'Generate Worm' > ``` worm.vbs ```


- - - -

## Perform Static Malware Analysis ##
Static Malware Analysis, also known as code analysis, involves going through the executable binary code without executing it to gain a better understanding of the malware and its purpose.

### Online Malware Scanning ###
#### VirusTotal ####
http://www.virustotal.com/. VirusTotal aims to improve the AV and security industry and make the Internet a safer place through the development of free tools and services. It simply acts as an information aggregator. The aggregated data are the output of different AV engines, website scanners, file and URL analysis tools, and user contributions.

#### Other Local and Online Malware Scanning Tools ####
* Hybrid Analysis (https://www.hybrid-analysis.com)
* Cuckoo Sandbox (https://cuckoosandbox.org)
* Jotti (https://virusscan.jotti.org)
* Valkyrie Sandbox (https://valkyrie.comodo.com)


### Strings Search ###
Various strings that could represent the malicious intent of a program, such as reading the internal memory or cookie data, are embedded in the compiled binary code.

#### BinText ####
It is a text extractor than can extract text from any file. It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\String Searching Tools\`.

Browse the file, select 'Advanced View' and click 'Go'.

#### Other String Searching Tools ####
* FLOSS (https://www.fireeye.com)
* Strings (https://docs.microsoft.com)
* Free EXE DLL Resource Extract (http://www.resourceextract.com)
* FileSeek (https://www.fileseek.ca)


### Identify Packaging and Obfuscation Methods ###
#### PEid ####
It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\Packaging and Obfuscation Tools\`.

#### Other Packaging and Obfuscation Tools ####
* Macro_Pack (GitHub)
* UPX (https://upx.github.io)
* ASPack (http://www.aspack.com)


### Find the Portable Executable (PE) Information of a Malware Executable File ###
The Portable Executable (PE) format is the executable file format used on Windows OS that stores the information a Windows system requires to manage the executable code. The PE stores metadata about the program, which helps in finding additional details of the file. For instance, the Windows binary is in PE format that consists of information such as time of creation and modification, import and export functions, compilation time, DLLs and linked files, as well as strings, menus and symbols.

#### PE Explorer ####
It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\PE Extraction Tools\`.

'File' > 'Open File'. 
* 'HEADERS INFO' (Document with Info bubble icon) - Allows you to view and save a text report on the file headers info, modify the entry point value, update the value of the checksum in the header, and set flag bits in the file header characteristics field.
* 'DATA DIRECTORIES' (Sublist icon next to the previous one) - Ability to view and edit the virtual address and size of the chosen directory.
* 'SECTION HEADERS' (Document with sublist icon) - View all sections and information about their location and size. Double click on a section to view the raw content.

#### Other PE Extraction Tools ####
* Portable Executable Scanner (pescan - https://tzworks.net)
* Resource Hacker (http://www.angusj.com)
* PEView (https://www.aldeid.com)


### Identify File Dependencies ###
#### Dependency Walker ####
It lists all dependent modules of an executable file and builds hierarchical tree diagrams. It also records all functions that each module exports and calls. Furthermore, it detects many common application problems such as missing and invalid modules, import and export mismatches, circular dependency errors, mismatched machine modules, and module initialization failures.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\File Dependency Tools\`.

#### Other Depdendency Checking Tools ####
* Dependency-check (https://jeremylong.github.io)
* Snyk (https://snyk.io)
* Hakiri (https://hakiri.io)
* RetireJS (https://retirejs.github.io)


### Perform Malware Disassembly ###
#### IDA Pro ####
It's a disassembler: It explores binary programs, for which the source code might not be available, to create maps of their execution. The primary purpose of a disassembler is to display the instructions actually executed by the processor in a symbolic representation called 'assembly language'. The debugger in IDA complements the static analysis capabilities of the disassembler. By allowing an analyst to single-step through the code being investigated, the debugger often bypasses the obfuscation.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\Disassembling and Debugging Tools\`.

* View > Graphs > Flow Chart - The flow of the application
* HEX
* Structures

#### OllyDbg ####
OllyDbg is a debugger that emphasizes binary code analysis, which is useful when source code is unavailable. It traces registers, recognizes procedures, API calls switches, tables, constants and strings, and locates routines from object files and libraries.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\Disassembling and Debugging Tools\`.

View:
  * Log Data
  * Executable Modules
  * Memory Map
  * CPU - Main Thread, Module Ntdll
  * Threads
  * Windows
  * Handles
  * SEH Chain
  * Call Stack
  * Breakpoints
  * Watches
  * References
  * Run Trace
  * Source
  * Source Files

#### Other Disassembling and Debugging Tools ####
* Ghidra (https://ghidra-sre.org)
* Radare2 (https://rada.re)
* WinDbg (http://www.windbg.org)
* ProcDump (https://docs.microsoft.com)


- - - -

## Perform Dynamic Malware Analysis ##
Dynamic Malware Analysis, also known as behavioral analysis, involves executing malware code to learn how it interacts with the host system and its impact after infecting the system. 

### TCP/IP Connections / Ports Monitoring ###
#### TCPView ####
Allows viewing processes and their PID, Protocol, Local Address, Local Port, Remote Address, Remote Port, State, Sent Packets, Sent Bytes... It allows to end the process and look at its properties.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Port Monitoring Tools\`.

#### CurrPorts ####
Allows viewing processes and their Name, PID, Protocol, Local Address, Local Port, Remote Address, Remote Port... It allows to kill the process and look at its properties.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Port Monitoring Tools\`.

#### Other Port Monitoring Tools ####
* Port Monitor (https://www.port-monitor.com)
* TCP Port Monitoring (https://www.dotcom-monitor.com)
* PortExpert (http://www.kcsoftwares.com)


### Process Monitoring ###
#### Process Monitor ####
Monitoring tool for Windows that shows the real-time file system, Registry and process thread activity. It combines features of two legacy Sysinternals utilities, Filemon and Regmon. It adds an extensive list of enhancements including rich and non-destructive filtering, comprehensive event properties such as session IDs and usernames, reliable process information, full thread stacks with integrated symbol support for each operation, and simultaneous logging into a file.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Process Monitoring Tools\`.

#### Other Process Monitoring Tools ####
* Process Explorer (https://docs.microsoft.com)
* OpManager (https://www.manageengine.com)
* Monit (https://mmonit.com)
* ESET SysInspector (https://www.eset.com)


### Registry Monitoring ###
#### Regshot ####
It compares the registry entries of two system state shots.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Registry Monitoring Tools\`.

### jv16 PowerTools ###
It cleans out unneeded files and data, cleaning the Windows registry, automatically fixing system errors, and applying optimization to the system. It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Registry Monitoring Tools\`.

Main Tools:
  * Clean and Speedup My Computer
  * Uninstall Software and Leftovers
  * Control Which Programs Start Automatically
  * Speed Up My Computer's Startup
  * Immunize My Computer
  * Pictures AntiSpy
  * Windows AntiSpy
  * Check for Vulnerable Software
  * Startup Timer

Registry Tools:
  * Registry Cleaner
  * Registry Finder
  * Registry Find & Replace
  * Registry Manager
  * Registry Monitor
  * Registry Information
  * Registry Compactor

File Tools:
  * File Cleaner
  * Duplicate File Finder
  * File Finder
  * Find and Repalce Data Inside Files
  * File Organizer
  * File Recovery
  * File Tool
  * Directory Finder
  * Directory Tool
  * Remove Files on Reboot
  * Merge Files
  * Split Files
  * Wipe Files
  * (...)

Privacy Tools:
  * Check for Vulnerable Software
  * Pictures AntiSpy
  * Windows AntiSpy
  * History Cleaner
  * Immunize my Computer
  * Service Manager
  * Disk Wiper
  * Automation Tool

#### Other Registry Monitoring Tools ####
* Reg Organizer (https://www.chemtable.com)
* Registry Viewer (https://accessdata.com)
* RegScanner (https://www.nirsoft.net)
* Registrar Registry Manager (https://www.resplendence.com)


### Windows Services Monitoring ###
#### Windows Service Manager (SrvMan) ####
SrvMan can detect changes in services and scan for suspicious Windows services.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Windows Services Monitoring Tools\`.

'User Account Control' > Yes. Then the 'Service Manager' main window appears listing all services available or running on the machine. You can stop or delete the service, restart it, add a new one...

#### Other Windows Services Monitoring Tools ####
* Advanced Windows Service Manager (https://securityxploded.com)
* Process Hacker (https://processhacker.sourceforge.io)
* Netwrix Service Monitor (https://www.netwrix.com)
* AnVir Task Manager (https://www.anvir.com)


### Startup Programs Monitoring ###
#### Autoruns for Windows ####
Allows viewing processes, dlls, services, logons, explorer applications, drivers, codecs... that run during system bootup or login (startup folder, Run registry key, RunOnce registry key...). 

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Windows Startup Programs Monitoring Tools\`.

#### WinPatrol ####
WinPatrol helps in monitoring the system and its files. It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Windows Startup Programs Monitoring Tools\`.

* Startup Programs
* Active Tasks
* IE Helpers - Browser plugins
* Services
* File Types
* Hidden Files
* Cookies
* File Size Monitor
(...)

#### Other Windows Startup Programs Monitoring Tools ####
* Autorun Organizer (https://www.chemtable.com)
* Quick Startup (https://www.glarysoft.com)
* StartEd Pro (http://www.outertech.com)
* Chameleon Startup Manager (http://www.chameleon-managers.com)


### Installation Monitoring ###
#### Mirekusoft Install Monitor ####
It aids in detecting and uninstalling hidden and background installations. It provides detailed info about the software installed, including how much disk space, CPU and memory they are using.

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Installation Monitoring Tools\`.

#### Other Installation Monitoring Tools ####
* SysAnalyzer (https://www.aldeid.com)
* Advanced Uninstaller Pro (https://www.advanceduninstaller.com)
* Revo Uninstaller Pro (https://www.revouninstaller.com)
* Comodo Programs Manager (https://www.comodo.com)


### Files and Folder Monitoring ###
#### PA File Sight ####
It helps in monitoring files and folders to detect any malware installed and any system file modifications. It blocks compromised computers on the network from reaching internal files, detects users copying files and can block their access, real-time alerts, audits who is deleting, moving and reading files...

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Files and Folder Monitoring Tools\`.

#### Other File and Folder Monitoring Tools ####
* Tripwire File Integrity and Change Manager (https://www.tripwire.com)
* Netwrix Auditor (https://netwrix.com)
* Verisys (https://www.ionx.co.uk)
* CSP File Integrity Checker (https://www.cspsecurity)


### Device Drivers Monitoring ###
#### DriverView ####
It displays a list of all device drivers currently loaded on the system and you can look at its properties. It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Device Drivers Monitoring Tools\`.

#### Driver Booster ####
Provides a better way to update outdated drivers on the system. It can also cleanup the system for optimization. It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\Device Drivers Monitoring Tools\`.

#### Other Device Drivers Monitoring Tools ####
* Driver Reviver (https://www.reviversoft.com)
* Driver Easy (https://www.drivereasy.com)
* Driver Fusion (https://treexy.com)
* Driver Genius (http://www.driver-soft.com)


### DNS Monitoring ###
#### DNSQuerySniffer ####
DNSQuerySniffer is a network sniffer that shows the DNS queries sent on your system. It displays all the DNS info of each query, request and response times, duration...

It can be found at: `Module 07 Malware Threats\Malware Analysis Tools\Dynamic Malware Analysis Tools\DNS Monitoring Tools\`.

#### Other DNS Monitoring Tools ####
* DNSstuff (https://www.dnsstuff.com)
* DNS Lookup Tool (https://www.ultratools.com)
* Sonar Lite (https://constellix.com)


- - - -

## Removing Malware ##
### Clamwin ###

* Memory Scan
* Scan a Drive - Select the drive and click 'Scan'
