# Windows Update Services Blocker (W10 / W11)

 This service stops Windows Update and Windows Update Medic services at the specified intervals.
 If not configured in the wupblocker.conf file, the default value is 60.

 The wupblocker.conf file is a plain text file that should be in the installation directory.
  You have to write in the FISRT LINE of the config file.

 Accepted values (integer): 30-600
 If value is 0, the service stops itself.

 This value measured in second.

 - [Files](#files)
 - [Event numbers](#event-numbers-and-messages)
 - [Pictures](#services-servicesmsc)
 - [Requirements](#requirements)
 - [Installation](#installation)
 - [Uninstallation](#uninstallation)
 - [Virustotal Results](#virustotal)
 - [Trobleshooting](#troubleshooting)

## Files

 Files in installed folder:

 - WindowsUpdateBlocker.exe - service file (cannot execute directly)
 
 - WindowsUpdateBlockerCleanup.exe - a little console utility to resetting Windows Update and Windows Update Medic services to their defaults. This utility also stopping Windows Update Blocker Service.
 
### You can use 3 switches (run as Administrator to take effects)
 
 WindowsUpdateBlockerCleanup.exe /h - Help
 
 WindowsUpdateBlockerCleanup.exe /s - Silently reset Windows Update Services without any prompt
 
 WindowsUpdateBlockerCleanup.exe /r - Try to restart Windows Update Service and Windows Update Medic Service (if exists)
 
 When You uninstall the service with  Uninstall.exe or Apps&Services remove method, the uninstaller process starts this utility to reset services.

## Event numbers and messages

You can view service events in the Events Log > Apps&Services > WUP Blocker tree.

### Windows Update Blocker Service Starting
 
- 100 - Starting Windows Update Blocker Service
- 110 - Windows Update Blocker Service started successfully
 
### Stopping Windows Update Services
 
- 200 - Attempting to stop Windows Update Services
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

[To top](#windows-update-services-blocker-w10--w11)

## Services (services.msc)

![02-Service](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/8730d714-e2bd-4780-8fd2-55f142ac4b86)

## EventLog (eventvwr.msc)

![03-EventLog](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/62a7f67b-86fd-4538-8e63-ef7977fed3f2)

## Task Manager (taskmgr.exe)

![04-TaskManager](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/6134f2ba-82b2-47ed-b70d-2d898bce337a)

[To top](#windows-update-services-blocker-w10--w11)

## Requirements

- Windows 10 / Windows 11 operating system
- .NET Framework v4.5

## Search or apply Windows Update

Start **WindowsUpdateBlockerCleanup.exe** as administrator.

This utility stops Windows Update Blocker Service and resetting Windows Update and Windows Update Medic Service (if exists).

- set startup mode to Automatic
- set service's user account to LocalSystem

## Installation

### Important!
Always install to **dedicated subdirectory**.

 1. Execute installer as Administrator. (important)
 2. Select install directory.
 3. After installing, press Win+R > type services.msc into the run dialog > press Enter.
 4. Search / check Windows Update Services Blocker (wupblocker)
 5. Start service.
 6. That's all.

 Note: if You want to search or apply a Windows Update, stop the service and run WindowsUpdateBlockerCleanup.exe as administrator.

![01-Setup-1](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/a0fc739c-801e-4a38-93ff-acf9465a934d)

![01-Setup-2](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/1b072c02-b1ab-4c4f-9c74-bf09621a4469)

![01-Setup-3](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/28bb587d-ee0c-401d-8c52-252f5ed1328a)

![01-Setup-4](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/46620f86-08dc-48f2-9127-32525b195bc9)

[To top](#windows-update-services-blocker-w10--w11)

## Uninstallation

 Execute uninstall.exe in install directory.
 
 or
 
 Find Windows Update Services Blocker in Settings > Apps&Services
 
 or 
 
 Uninstall using the old Control Panel method. (control.exe)

 [To top](#windows-update-services-blocker-w10--w11)

## Tested 

 - Windows 10 x64 Professional 22H2
 - Windows 11 x64 Professional 22H2
 - Windows 11 x64 Professional for Workstation 22H2

## Virustotal

- Setup-WUPSvcBlocker.v1.0.0.2.exe (created with InstallBuilder)
- Detection: 12 / 71 (08/19/2023)

### Link
#### https://www.virustotal.com/gui/file/667d799c7e3ee8d763c1e97cc9f182bf03878582f54e52ceffdc0fa50cf91017?nocache=1

_______________________________________________________________________

- WindowsUpdateBlocker.exe
- Detection: 2 / 71 (08/19/2023)

### Link
#### https://www.virustotal.com/gui/file/c747a23940372145a05f803df25556d271f4081e733b7c79a744817192e9ddfc?nocache=1

_______________________________________________________________________

- WindowsUpdateBlockerCleanup.exe
- Detection: 3 / 71 (08/19/2023)

### Link
#### https://www.virustotal.com/gui/file/c9c30b8acdea03189b627655c77b0ea3d99332e88658cae34be504e59ab0f29b?nocache=1

[To top](#windows-update-services-blocker-w10--w11)

_______________________________________________________________________

## Troubleshooting

If Service not working (ex. won't start etc.), check Your antivirus or other protection software.

You can view detailed result in the EventLog (eventvwr.msc) > Windows logs > Application (Source: wupblocker)

[To top](#windows-update-services-blocker-w10--w11)

_______________________________________________________________________

No spyware, ransomware, malware or any other harmful code inside.

_______________________________________________________________________

Service written in VB.NET (v4.5)

Programmed with love,
1983-2023, C2H5Cl, Hungary
