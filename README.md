user-daemon-system
====================

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

Install
-------

requirements: based on zsh.

	# install 'user-daemon-system-git' package from AUR. # pacaur -S user-daemon-system-git
	cp _zlogin ~/.zlogin
	cp _zhalt ~/.zhalt
	alias halt="/bin/zsh ~/.zhalt 2>/dev/null; sudo halt"
	alias reboot="/bin/zsh ~/.zhalt 2>/dev/null; sudo reboot"

Resources
---------

* [zcm](https://github.com/zcm/zcm): oh-my-zsh and Bundler inspried ZSH Configuration Manager.
