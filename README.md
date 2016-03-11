Gdog
====
A stealthy Python based backdoor that uses Gmail as a command and control server

This project was inspired by the gcat(https://github.com/byt3bl33d3r/gcat) from byt3bl33d3r.


Requirements
=====
* Python 2.x
* PyCrypto module


Setup 
=====
For this to work you need:
- A Gmail account (**Use a dedicated account! Do not use your personal one!**)
- Turn on "Allow less secure apps" under the security settings of the account.
- You may also have to enable IMAP in the account settings.


Contents
=====
- ```gdog.py``` a script that's used to enumerate and issue commands to available clients
- ```client.py``` the actual backdoor to deploy

You're probably going to want to compile ```client.py``` into an executable using [Pyinstaller](https://github.com/pyinstaller/pyinstaller)

**Note: It's recommended you compile client.py using a 32bit Python installation**


Usage
=====
