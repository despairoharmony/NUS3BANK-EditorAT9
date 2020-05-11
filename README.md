# NUS3BANK Editor
### TO USE THIS TOOL PROPELY YOU NEED at9tool.exe FROM SONY SDK
### PLACE AT exeLib FOLDER
_by jam1garner (1.0-1.7 then support) and BlueDan aka BDS aka DanSyor (1.7-now)_

_fork made by DespairOfHarmony_

This is a GUI for Windows users to convert and import audio tracks into nus3bank files, made specially for Taiko no Tatsujin V Version for PS Vita. Nus3bank files are basically a set of at9 audio tracks (for bgm, they most likely have only one track) that can feature a loop or not.

You need Python 2.7 installed to run it. Or since 2.20, Python 3.5! [Official Python website](https://www.python.org/)

Run `NUS3BANK Editor.pyw` either on your file explorer or on console.
Or since 2.10 you can use `NUS3BANK_Editor.bat`, that you can bind to be the default program to open files with nus3bank extension.


### Credits:
- Soneek who made tools essential for this
- Alex Barney for VGAudio (https://github.com/Thealexbarney/VGAudio)
- everyone involved with vgmstream
- everyone involved with ffmpeg
- everyone who tested this tool and gave feedback

### Known issues:
* You might have encoding problems (some error window popping up yelling at you something about UnicodeEncodeError) related to characters within the paths of files you're using. I try my best for you to avoid those but unfortunately the behaviour doesn't seem consistent from one computer to another, making it hard for me to clearly identify what goes wrong. If you're using Python 2.7 and encounter these issues, either be careful about any potentially exotic character in the paths of your files, or consider switching to Python 3.5.


### About versions available and development
Last public "true" release was [2.13b](http://gbatemp.net/threads/easy-nus3bank-editor-with-gui.426370/page-8#post-6415721) with [util hotfix](http://gbatemp.net/threads/easy-nus3bank-editor-with-gui.426370/page-9#post-6416683). Yet, I'd recommend 2.20-pre, so don't expect broken download links for versions anterior to it to get fixed.

2.20 has never been released "for real" but you can download the [zip](https://github.com/DanSyor/NUS3BANK-Editor/archive/master.zip) for the master branch on the [main page for the Github project](https://github.com/DanSyor/NUS3BANK-Editor) for "2.20-pre" nightlies, it should be stable enough.

Despite the lack of recent updates/commits, I've started a rewrite on my own some time ago so expect a major update some day, but I can't give an ETA. (next release won't be 2.20 - which will effectively never get a real release - but 3.00)
Here are some planned features:
- NUS3BANK creation, with only a few general files required, no injection needed (can be useful especially for music)
- in-app player
- true sound editor (custom loop)
- cleaner/true injection (might fix some weird behaviors)
- more control on nus3bank container (incl. track renaming, pointer management)

### Troubleshooting
Be sure to grab the latest version, download links on the original [GBATemp Thread](http://gbatemp.net/threads/easy-nus3bank-editor-with-gui.426370/) may be outdated but you can still ask for help there.
Future releases will be available on [Github](https://github.com/DanSyor/NUS3BANK-Editor/releases).

If you encounter any error, please provide (on the above thread or PM BlueDan on Discord) a clear and detailed explanation of what you're attempting to achive and how you do so. A screenshot of the error is highly appreciated.

You may want to use NUS3BANK_Editor_troubleshooting.bat to have a better chance to screenshot any error.
 * "When trying to use NUS3BANK_Editor.bat, an error pops up: ``Windows cannot find 'pythonw'. Make sure you typed the name correctly, and then try again.``
  * Looks like Python is not in your environment variable PATH. Follow the following instructions (these are for Python 2.7):
        - Run the Python installer, pick `Change Python` or `Modify`
        - At `Customize Python` assure you enable `Add python.exe to Path` and complete the process
        - It should now work. If it doesn't, go on.
        - Right click on the windows logo (or hit windows + pause and go to step 6)
        - Select system
        - Select advanced settings
        - Environment variables
        - Find path, click edit
        - Select new and enter `C:\Python27` (Note: this path may change depending on your installation or your version of Python; there should be a file called python.exe in that directory)
        - Select new (again) and enter `C:\Python27\Scripts` (Note: this path may change depending on your installation)
        - Select OK in all these windows
        - If you have any cmd opened, you should close them before checking your %path% again
        - Try first with user variables (which should be enough) then system variables
 * "I'd like to run the Python 3.5 version, how do I do that?"
  * You can uninstall Python 2 and install Python 3. Yet, you might wish to keep Python 2 installed and be able to chose which version of python you want to use.
    - Go to `C:\Python27` (or wherever your Python 2 installation is).
    - There sould be `python.exe` and `pythonw.exe`. Copy and and paste them into the same directory.
    - Rename these copies `python2.exe` and `pythonw2.exe` (respectively)
    - Go to `C:\Users\<your username>\AppData\Local\Programs\Python\Python35` (or wherever your Python 3 installation is). If you don't know where your installation is you can either:
        - do `echo %path%` in a cmd window (assuming Python 3 is in your path environment variable) and locate the part about Python 3
        - run the installer again, select `Modify` and check the directory
        - `System` > `Advanced settings` > `Environment Variables` > Look for `Path` > Look for Python 
    - There sould be `python.exe` and `pythonw.exe`. Copy and and paste them into the same directory.
    - Rename these copies `python3.exe` and `pythonw3.exe` (respectively)
    - With this setup you can chose to load Python 2 by typing `python2` or Python 3 by typing `python3` in a cmd window or within a batch file. This will also so called idle Python 2 (resp. Python 3) to be forced with `pythonw2` (resp. `pythonw3`). (idle is Python with no console: if you double click a file with py extension it will be run with a console, if you double click the same file by changing its extension by pyw, it will run with no console)
    - To change which version is the "default" one (`python` and `pythonw` for cmd window or bat files, probably not default program for opening .py or .pyw files): `System` > `Advanced settings` > `Environment Variables` > Look for `Path` (in user variables) it should have both versions, if it doesn't, remove `C:\Python27` entry from the global path and add it back to the user path. The default version will be which one is higher between `C:\Python27` and `C:\Users\<your username>\AppData\Local\Programs\Python\Python35`.
    - To change which version is run with `NUS3BANK_Editor.bat`, edit it and replace `pythonw` with either `pythonw2` or `pythonw3`

[Version history](HISTORY.md)
