node-startup
============

Startup script for Linux-based systems for running 'grunt server' or any other command  when rebooting from /etc/init.d script.

Set the APP_DIR and CMD variables in init.d/node-app.
	
Copy the startup script node-app to your /etc/init.d directory

	sudo bash -l
	cp ./init.d/node-app /etc/init.d/


Test that it all works:

	/etc/init.d/node-app start
	/etc/init.d/node-app status
	/etc/init.d/node-app restart
	/etc/init.d/node-app stop

Add node-app to the default runlevels

	update-rc.d node-app defaults

Finally, reboot to be sure app starts automatically

	reboot

Supported OS
----

Tested with Debian 6.0, but it should work on other Linux systems that use startup scripts in /etc/init.d (Redhat, CentOS, Gentoo, Ubuntu, etc).

Gotchas
----

If there is a app.pid file already, but node is not running, and you try to start it will not start. You will have to manually remove the .pid file and run it again.

I will add a --force in the near future.

LICENSE
----

(The MIT License)

