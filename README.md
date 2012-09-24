user-daemon-system, The missing daemon system for user.
==============================================================

|                |                                                      |
|----------------|------------------------------------------------------|
| Homepage:      | https://github.com/GutenYe/user-daemon-system        |
| Author:	       | Guten                                                |
| License:       | MIT-LICENSE                                          |
| Issue Tracker: | https://github.com/GutenYe/user-daemon-system/issues |

Archlinux initscripts.

|  initscripts 	         | user-daemon-system   |
|------------------------|----------------------|
| /etc/rc.conf           | ~/etc/rc.conf        |
| /etc/rc.d/ 	           | ~/etc/rc.d           |
| /etc/rc.d/functions    | ~/etc/rc.d/functions |
|                        |                      |
| /var/run/              | ~/var/run/           |
| /var/run/daemons/      | ~/var/run/daemons/   |
| /var/log/              | ~/var/log/           |
| /var/cache/            | ~/var/cache/         |

**Avaliable daemons**:

* [user-mpd-daemon](https://aur.archlinux.org/packages.php?ID=56855): mpd is a flexible, powerful, server-side music player daemon.
* [user-aria2-daemon](https://aur.archlinux.org/packages.php?ID=56854): aria2 is a lightweight multi-protocol & multi-source download utility operated in command-line
* [user-profile-sync-daemon](https://aur.archlinux.org/packages.php?ID=62147): sync browser profiles to tmpfs.

Getting Started
-----
	
install a user daemon.

	$ pacaur -S user-mpd-daemon  # need run as normal user. it install files to $HOME.

start daemon when a user logged in.

	$ bash -l
	# will start all DAEMONS defined in ~/etc/rc.conf for use foo

stop daemons when system halted.

	$ halt
	# stop all running daemons for all users.

manualy stop daemon

	$ ~/etc/rc.d/food stop

Install
-------

	$ pacaur -S user-daemon-system-git

	# ~/.bash_login    (ZSH: ~/.zlogin)
		user-daemon-system start

	# /etc/rc.local.shutdown
		/usr/bin/user-daemon-system stop-all

Note on Patches/Pull Requests
-----------------------------

1. Fork the project.
2. Make your feature addition or bug fix.
3. Add tests for it. This is important so I don't break it in a future version unintentionally.
4. Commit, do not mess with rakefile, version, or history. (if you want to have your own version, that is fine but bump version in a commit by itself I can ignore when I pull)
5. Send me a pull request. Bonus points for topic branches.

Credits
--------

* [Contributors](https://github.com/GutenYe/user-daemon-system/contributors)

Resources
---------

* [user-initscripts](https://github.com/fleger/user-initscripts) A user daemon system based on and relying upon the Arch Linux initscripts.

Copyright
---------

(the MIT License)

Copyright (c) 2011-2012 Guten

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
