user-daemon-system, The missing daemon system for user.
==============================================================

| Homepage:      |  https://github.com/GutenYe/user-daemon-system       |
|----------------|------------------------------------------------------       |
| Author:	       | Guten                                                 |
| License:       | MIT-LICENSE                                                |
| Issue Tracker: | https://github.com/GutenYe/user-daemon-system/issues |

Overview
--------

ArchLinux already has a daemon system at /etc/rc.d/, while this is for user.

	~/etc/
		rc.conf
	  conf.d/
	  rc.d/

	~/var/
	  run/
	  log/
	  cache/

How it works, when user login with zsh, ~/.zlogin starts all the daemons defined in DAEMONS array in ~/etc/rc.conf, when user call `halt` command, stop all the daemons and shutdown the computer.

Why we need a user based daemon system? for aria2c daemon as example, put aria2c into system daemon is not good, evey user can start/stop their own aria2c daemon.

more see [user-aria2d](https://github.com/GutenYe/user-aria2d) for an example.

Usage
-----
	
boot system

	$ zsh -l
	# will start all DAEMONS defined in ~/etc/rc.conf

halt system

	$ . ~/.zhalt && halt
	# stop all running daemons.

manualy start daemon

	$ ~/etc/rc.d/food start

Install
-------

Requirements: Archlinux, zsh

	# install 'user-daemon-system-git' package from AUR.
	pacaur -S user-daemon-system-git
	cp _zlogin ~/.zlogin
	cp _zhalt ~/.zhalt
	alias halt="/bin/zsh ~/.zhalt 2>/dev/null; sudo halt"
	alias reboot="/bin/zsh ~/.zhalt 2>/dev/null; sudo reboot"

for zcm user.

	pacaur -S user-daemon-system-git

Contributing
-------------

* Feel free to join the project and make contributions (by submitting a pull request)
* Submit any bugs/features/ideas to issue tracker

Credits
--------

* [Contributors](https://github.com/GutenYe/user-daemon-system/contributors)

Resources
---------

* [zcm](https://github.com/zcm/zcm): oh-my-zsh and Bundler inspried ZSH Configuration Manager
* [pacuaer](https://github.com/Spyhawk/pacaur): A fast workflow AUR wrapper using cower as backend
* [zsh](http://zsh.sourceforge.net): the final shell
* [Archlinux](http://www.archlinux.org): A simple, lightweight distribution

Copyright
---------

(the MIT License)

Copyright (c) 2011 Guten

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
