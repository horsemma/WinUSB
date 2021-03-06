# WinUSB
[![WinUSB Version](https://img.shields.io/badge/winusb-1.0.11-orange.svg)](https://github.com/slacka/WinUSB) 
[![WinUSB License](https://img.shields.io/badge/license-gpl-blue.svg)](https://github.com/slacka/WinUSB/blob/master/COPYING) 

<img src="winusb.jpg" align="right" />
<br>
_A Linux program to create Windows USB stick installer from a real Windows DVD or an image._

This package contains two programs:

* WinUSB-gui: a simple tool that enable you to create
	 your own usb stick windows installer from iso image
	 or a real DVD.
* winusb: the command line tool.

Supported images:

Windows Vista, Windows 7, Window 8, Windows 10. All languages and any version (home, pro...) and Windows PE are supported.

Supported bootmodes:

* Legacy/MBR-style/IBM PC compatible bootmode
* Native UEFI booting is supported for Windows 7 and later images(with a limitation of only FAT filesystem can be used as target filesystem)

This project is a fork of [Congelli501's WinUSB software](http://en.congelli.eu/prog_info_winusb.html), which is not maintained since 2012, according to the official website.

## Installation
Following is the instructions to install WinUSB if your Linux distro's packaged version is not available or too old.

### Acquire WinUSB's source code
Choose one of the following method:

* Download and extract source code archive from GitHub
* Cloning WinUSB's Git repository to local machine using `git clone https://github.com/slacka/WinUSB.git`

### Install WinUSB's build dependencies
```shell
# For Ubuntu
$ sudo apt-get install devscripts equivs gdebi-core
$ cd <WinUSB source code directory>
$ mk-build-deps debian/control # NOTE: Currently due to Debian Bug #679101 this command will fail if source path contains spaces.
$ sudo gdebi winusb-build-deps_<version>_all.deb

# For Fedora
$ sudo dnf install wxGTK3-devel
```
### Build & install WinUSB
```shell
# For Ubuntu
$ dpkg-buildpackage -uc -b # NOTE: Currently due to bug in the build system this command will fail if source's path contains space or single quotes, refer issue #84 for details
$ sudo gdebi ../winusb_<version>_<architecture>.deb

# Generic method
./configure
make
sudo make install
```

## License
winusb is sold under [GPL licence](https://github.com/slacka/WinUSB/blob/master/COPYING).
