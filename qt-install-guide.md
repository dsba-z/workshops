# Guide for installing Qt

Qt online installer doesn't work with Russian IPs. Probably the easiest way to fix this is to use a VPN and still install Qt with the online installer.

Other than that, **alternative** methods are:

## Use a package manager

### MacOS

Install Homebrew - https://brew.sh/

Run `brew install qt` in Terminal.

### Linux

Use the package manager of your Linux distribution.
## Use Offline Installer

Here is a list of official Qt mirrors. These install Qt 5.12.12, a slightly older version which should be fine for the project and the workshops.

Instead of using your Qt account you can disconnect from the Internet or change settings in the installer to disable connections.

### MacOS

https://ftp.acc.umu.se/mirror/qt.io/qtproject/archive/qt/5.12/5.12.12/qt-opensource-mac-x64-5.12.12.dmg  
https://mirrors.dotsrc.org/qtproject/archive/qt/5.12/5.12.12/qt-opensource-mac-x64-5.12.12.dmg  
https://ftp.fau.de/qtproject/archive/qt/5.12/5.12.12/qt-opensource-mac-x64-5.12.12.dmg  
https://qt-mirror.dannhauer.de/archive/qt/5.12/5.12.12/qt-opensource-mac-x64-5.12.12.dmg  
https://mirror.netcologne.de/qtproject/archive/qt/5.12/5.12.12/qt-opensource-mac-x64-5.12.12.dmg  
https://ftp1.nluug.nl/languages/qt/archive/qt/5.12/5.12.12/qt-opensource-mac-x64-5.12.12.dmg  
https://ftp2.nluug.nl/languages/qt/archive/qt/5.12/5.12.12/qt-opensource-mac-x64-5.12.12.dmg  
https://mirrors.ukfast.co.uk/sites/qt.io/archive/qt/5.12/5.12.12/qt-opensource-mac-x64-5.12.12.dmg  


### Windows

https://ftp.acc.umu.se/mirror/qt.io/qtproject/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe
https://mirrors.dotsrc.org/qtproject/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe
https://ftp.fau.de/qtproject/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe
https://qt-mirror.dannhauer.de/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe
https://mirror.netcologne.de/qtproject/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe
https://ftp1.nluug.nl/languages/qt/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe
https://ftp2.nluug.nl/languages/qt/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe
https://mirrors.ukfast.co.uk/sites/qt.io/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe



# Connecting Qt to Qt Creator.

To use Qt in Qt Creator you need to configure your **kit** for it. To do so, open "Tools" -> "Settings" -> "Kits (first item in the list on the left)" -> "Qt Versions (a tab on the right)"

If you already have Qt there, Qt is installed and configured.

If you don't have any Qt versions there, but you installed it via one of the previous methods, click "Add..." on the right. Navigate to the Qt installation, locate the executable file `qmake` (`qmake.exe` on Windows) and select this file.

Go to the tab "Kits" and check that the Kit you use has something selected in the field "Qt version". If you have a Qt version there, everything should work.
