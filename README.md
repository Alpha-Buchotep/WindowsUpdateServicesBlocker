# Windows Update Services Blocker (W10 / W11)

 This service stops Windows Update and Windows Update Medic services at the specified intervals.
 If not configured in the wupblocker.conf file, the default value is 60.

 The wupblocker.conf file is a plain text file that should be in the installation directory.
  You have to write in the FISRT LINE of the config file.

 Accepted values (integer): 30-600
 If value is 0, the service stops itself.

 This value measured in second.


 - [Event numbers](#event-numbers-and-messages)
 - [Pictures](#services-servicesmsc)
 - [Installation](#installation)
 - [Uninstallation](#uninstallation)
 - [Virustotal Results](#virustotal)
 - [Trobleshooting](#troubleshooting)


 You can view service events in the Events Log > Apps&Services > WUP Blocker tree.

## Event numbers and messages

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

## Services (services.msc)

![02-Service](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/8730d714-e2bd-4780-8fd2-55f142ac4b86)


## EventLog (eventvwr.msc)

![03-EventLog](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/62a7f67b-86fd-4538-8e63-ef7977fed3f2)

## Task Manager (taskmgr.exe)

![04-TaskManager](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/6134f2ba-82b2-47ed-b70d-2d898bce337a)

 
## Installation

 1. Execute installer as Administrator. (important)
 2. Select install directory.
 3. After installing, press Win+R > type services.msc into the run dialog > press Enter.
 4. Search / check Windows Update Services Blocker (wupblocker)
 5. Start service.
 6. That's all.

 Note: if You want to search or apply a Windows Update, stop the service.

![01-Setup-1](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/a0fc739c-801e-4a38-93ff-acf9465a934d)

![01-Setup-2](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/1b072c02-b1ab-4c4f-9c74-bf09621a4469)

![01-Setup-3](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/28bb587d-ee0c-401d-8c52-252f5ed1328a)

![01-Setup-4](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/46620f86-08dc-48f2-9127-32525b195bc9)


## Uninstallation

 Execute uninstall.exe in install directory.
 
 or
 
 Find Windows Update Services Blocker in Settings > Apps&Services
 
 or 
 
 Uninstall using the old Control Panel method. (control.exe)

## Tested 

 - Windows 10 x64 Professional 22H2
 - Windows 11 x64 Professional 22H2
 - Windows 11 x64 Professional for Workstation 22H2

## Virustotal

- Setup-WUPSvcBlocker.v1.0.0.1.exe
- Detection: 11 / 71 (08/13/2023)

### Link
#### https://www.virustotal.com/gui/file/e56665fbb5853d5744cb47da81a5888879f226148aff903968de922a632bbad1?nocache=1

_______________________________________________________________________

- WindowsUpdateBlocker.exe
- Detection: 2 / 71 (08/13/2023)

### Link
#### https://www.virustotal.com/gui/file/bf023804f4ca9bd53f8120815e214c6f73403ae07fdf472c45de955a1ffae9a4?nocache=1

_______________________________________________________________________

## Troubleshooting

If Service not working (ex. won't start etc.), check Your antivirus or other protection software.

You can view detailed result in the EventLog (eventvwr.msc) > Windows logs > Application (Source: wupblocker)

_______________________________________________________________________

No spyware, ransomware, malware or any other harmful code inside.

_______________________________________________________________________

Programmed with love,
1983-2023, C2H5Cl, Hungary
