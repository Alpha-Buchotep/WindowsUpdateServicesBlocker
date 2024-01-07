# Windows Update Services Blocker
### W7 / W8 / W10 / W11

### Version: 1.0.4.0

 This service stops Windows Update and Windows Update Medic services at the specified intervals plus kill Windows Update Orchestrator processes if running. (MoUsoCoreWorker.exe, USOCoreWorker.exe, USOClient.exe).
 If not configured in the wupblocker.conf file, the default value is 60 (sec).

 The wupblocker.conf file is a plain text file that should be in the installation directory.
 You have to write in the FISRT LINE of the config file.

 Accepted value (integer, sec): 30-600
 If value is 0, the service stops itself.

 
 **Service and helper utility written in VB.NET (v4.5)**


 - [Files](#files)
 - [Requirements](#requirements)
 - [Installation](#installation)
 - [Uninstallation](#uninstallation)
 - [Search or apply Windows Update](#search-or-apply-windows-update)
 - [Pictures](#pictures)
 - [Event numbers](#event-numbers-and-messages)
 - [Virustotal Results](#virustotal)
 - [Trobleshooting](#troubleshooting)

## Files

 Files in installed folder:

 - **WindowsUpdateBlocker.exe** - service file (cannot execute directly)
 
 - **WindowsUpdateBlockerCleanup.exe** - a little console utility to resetting Windows Update and Windows Update Medic services to their defaults. This utility also stopping Windows Update Blocker Service.
 
### You can use 3 switches (run as Administrator to take effects)
 
 **WindowsUpdateBlockerCleanup.exe /h** - Help
 
 **WindowsUpdateBlockerCleanup.exe /s** - Silently reset Windows Update Services without any prompt
 
 **WindowsUpdateBlockerCleanup.exe /r** - Try to restart Windows Update Service and Windows Update Medic Service (if exists)
 
 When You uninstall the service uninstaller process starts this utility to reset services to their defaults state.


## Requirements

- Windows 7 / Windows 8 / Windows 10 / Windows 11 operating system
- Minimum .NET Framework v4.5 or higher

### Tested 

 - Windows  7 x64 Ultimate
 - Windows  8 x64 Professional
 - Windows 10 x64 Professional 22H2
 - Windows 11 x64 Professional 22H2
 - Windows 11 x64 Professional for Workstation 22H2

[To top](#windows-update-services-blocker)


## Installation

### Important!
Always install to **dedicated subdirectory**.

**Uninstall any previous release!**

 1. Execute installer as Administrator. (important)
 2. Select install directory.
 3. That's all.

 Note: if You want to search or apply a Windows Update run WindowsUpdateBlockerCleanup.exe as administrator. (see above)

![Install-01](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/6bf10126-5745-4bda-b7ae-9a7c7f0a0fd4)

![Install-02](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/bf7d5aa2-4a8a-4a4b-8433-d4b2f326d201)

![Install-03](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/1f05288f-8eb8-457a-abaf-41a2b3052f20)

![Install-04](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/1ad79afe-bfe2-4cd1-a2a7-1ad3dc03fdea)

![Install-05](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/d619e51a-953d-4c36-91b8-7b54c4ec1532)

[To top](#windows-update-services-blocker)


## Uninstallation

 Execute Installer and choose Remove.
 
 or
 
 Find Windows Update Services Blocker in Settings > Apps&Services
 
 or 
 
 Uninstall using the old Control Panel method. (control.exe > Programs and Features or Win+R > appwiz.cpl)

 [To top](#windows-update-services-blocker)


## Search or apply Windows Update

If You want to search or apply a Windows Update do the following:

Start **WindowsUpdateBlockerCleanup.exe** as administrator and search for updates.

If You finished updating Windows and want to prevent automatic updates then start Windows Update Blocker Service (wupblocker).

### **Note**
This utility stops Windows Update Blocker Service and resetting Windows Update and Windows Update Medic Service (if exists).

- set startup mode to Automatic
- set service's user account to LocalSystem

![CleanUpUtility](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/e9f9ed5c-41ca-44ea-ba76-cb4c4b27aea7)

[To top](#windows-update-services-blocker)


## Pictures

### Services (services.msc)

![Service](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/1d6bb04a-9a9d-4738-842f-a0a2361e63af)


### EventLog (eventvwr.msc)

![03-EventLog](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/62a7f67b-86fd-4538-8e63-ef7977fed3f2)

### Task Manager (taskmgr.exe - Process Hacker)

![04-TaskManager](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/6134f2ba-82b2-47ed-b70d-2d898bce337a)

[To top](#windows-update-services-blocker)


## Event numbers and messages

You can view service events in the Events Log > Apps&Services > WUP Blocker tree.

### Windows Update Blocker Service Starting
 
- 100 - Starting Windows Update Blocker Service
- 110 - Windows Update Blocker Service started successfully
 
### Stopping Windows Update Services
 
- 200 - Attempting to stop Windows Update Services
- 201 - Process MoUsoCoreWorker.exe killed (if running)
- 202 - Process USOCoreWorker.exe killed (if running)
- 203 - Process USOClient.exe killed (if running)
- 210 - Windows Update Service stopped successfully
- 220 - Windows Update Medic Service stopped successfully
- 230 - Windows Update Service disabled successfully
- 240 - Windows Update Medic Service disabled successfully
- 245 - Windows Update Service disabled successfully in registry
- 246 - Windows Update Medic Service disabled successfully in registry
- 247 - Windows Update Service account successfully changed to Guest
- 248 - Windows Update Medic Service account successfully changed to Guest
- 250 - Windows Update Service already stopped
- 260 - Windows Update Medic Service already stopped
- 270 - Windows Update Service already disabled
- 275 - Windows Update Service account already changed to Guest
- 280 - Windows Update Medic Service already disabled
- 285 - Windows Update Medic Service account already changed to Guest

### Windows Update Blocker Service Stopping

- 300 - Stop Windows Update Blocker Service manually
- 310 - Windows Update Blocker Service stopped because of config file settings! (First line = 0)

### Config file errors

- 400 - No config file found, using default values
- 410 - Error reading config file
- 420 - Invalid value in config file first line
 
### Windows Update Blocker Service Errors

- 500 - Cannot stop Windows Update Service
- 510 - Cannot stop Windows Update Medic Service
- 520 - Cannot disable Windows Update Service
- 530 - Cannot disable Windows Update Medic Service
- 535 - Cannot disable Windows Update Service in registry
- 536 - Cannot disable Windows Update Medic Service in registry
- 537 - Cannot change Windows Update Service account to Guest
- 538 - Cannot change Windows Update Medic Service account to Guest
- 540 - Windows Update Service state unknown
- 550 - Windows Update Medic Service state unknown

[To top](#windows-update-services-blocker)


## Virustotal

- Setup-WUPSvcBlocker.v1.0.4.0.exe
- Detection: 11 / 69 (07/01/2024)

### Link
#### https://www.virustotal.com/gui/file/35ccf4036b260143833782adeb3a2b0ed14da003288bb166f186647dac54ef93?nocache=1

_______________________________________________________________________

- WindowsUpdateBlocker.exe
- Detection: 0 / 69 (07/01/2024)

### Link
#### https://www.virustotal.com/gui/file/3eb5a07df7a940a3f039600a540045005b0e23d5aea42cceab379ef53882c5d7?nocache=1

_______________________________________________________________________

- WindowsUpdateBlockerCleanup.exe
- Detection: 3 / 72 (07/01/2024)

### Link
#### https://www.virustotal.com/gui/file/1911cad441298487cecc64e9b8590fe323a329ad7e0fd3ac030ea40b722f8ab9?nocache=1

[To top](#windows-update-services-blocker)

_______________________________________________________________________

## Troubleshooting

If Service not working (ex. won't start etc.), check Your antivirus or other protection software.

Maybe service blocked by Your AntiVirus / HIPS / other protection software (service executable quarantinized / sandboxed / blocked / deleted)

You can view detailed information about service related events in the EventLog (eventvwr.msc) > Windows logs > Application (Source: wupblocker)


[To top](#windows-update-services-blocker)

_______________________________________________________________________

No spyware, ransomware, malware or any other harmful code inside.

_______________________________________________________________________

Programmed with love,
1983-2023, C2H5Cl, Hungary
