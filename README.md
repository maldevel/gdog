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
* Encrypted transportation messages
* Retrieve system information
* Retrieve Geolocation information
* Retrieve list of clients
* Execute system command
* Download files from client 
* Upload files to client
* Execute shellcode
* Take screenshot
* Lock client's screen 
* Keylogger


Setup
=====
For this to work you need:
- A Gmail account (**Use a dedicated account! Do not use your personal one!**)
- Turn on "Allow less secure apps" under the security settings of the account.
- You may also have to enable IMAP in the account settings.


Download/Installation
====
* git clone https://github.com/maldevel/gdog
* pip install -r requirements.txt --user


Contents
=====
- ```gdog.py``` a script that's used to enumerate and issue commands to available clients
- ```client.py``` the actual backdoor to deploy

You're probably going to want to compile ```client.py``` into an executable using [Pyinstaller](https://github.com/pyinstaller/pyinstaller)

**Note: It's recommended you compile client.py using a 32bit Python installation**


Improvements
=====
* AES Encryption
* SHA 256 Hashing
* Generate computer unique id using system information/characteristics (SHA256 hash)
* Retrieve more system information 
* Job IDs are random SHA256 hashes
* Retrieve Geolocation information (City, Country, lat, long, etc..)


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
  -download PATH        Download a file from a clients system
  -upload SRC DST       Upload a file to the clients system
  -exec-shellcode FILE  Execute supplied shellcode on a client
  -screenshot           Take a screenshot
  -lock-screen          Lock the clients screen
  -force-checkin        Force a check in
  -start-keylogger      Start keylogger
  -stop-keylogger       Stop keylogger
```
