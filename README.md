# Windows Update Blocker Service (W10 / W11)

 This service stops Windows Update and Windows Update Medic services at the specified intervals.

 If not configured in the wupblocker.conf file, the default value is 60.

 The wupblocker.conf file is a plain text file that should be in the installation directory.
 
 You have to write in the FISRT LINE of the config file.

 Accepted values (integer): 30-600
 
 If value is 0, the service stops itself.

 This value measured in second.

 You can view service events in the Events Log. Apps&Services > WUP Blocker tree.

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

![02-Service](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/c7d34ccc-2ec8-4008-8a7d-e234deae4a30)

## EventLog

![03-EventLog](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/c964504c-a6c0-49dc-a56c-5dc847dfa753)

 
## Installation

 1. Execute installer as Administrator (important)
 2. Select install directory.
 3. After installing, press Win+R > type services.msc into the run dialog > press Enter.
 4. Search / check Windows Update Services Blocker (wupblocker)
 5. Start service.
 6. That's all.

 Note: if You want to search or apply a Windows Update, stop the service.

![01-Setup-1](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/b6c42308-9a11-45cc-ad50-92d0c40df181)

![01-Setup-2](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/3b20b896-87e2-4af1-9e95-dbe0c2ced416)

![01-Setup-3](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/9df05b59-20ab-4dd0-9dc0-2037ebc6949d)

![01-Setup-4](https://github.com/Alpha-Buchotep/WUPBlocker/assets/63890454/4339e554-aadf-4b9f-85c8-92357bdc29e5)


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


Programmed with love,
1983-2023, C2H5Cl, Hungary
