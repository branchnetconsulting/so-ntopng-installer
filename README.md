# so1404-ntopng-installer
Script to install or upgrade to the latest stable ntopng from the official ntop repo, onto a Security Onion 14.04 sensor

The ntopng packages maintained at http://packages.ntop.org/ depend on the pfring package also maintained there.  However, Security Onion systems use a custom set of securityonion-pfring-* packages to satisfy pfring dependencies, and these cannot coexist with the pfring package from the ntop.org repo.  

This installer script fetches the needed content from the ntop repo, and then installs ntopng in a way that works cleanly on Security Onion sensors.

Requirement: Security Onion sensor running on Ubuntu 14.04 with a pfring version of 6.2.0 or higher.  If you haven't installed or soup-updated your Security Onion sensor since before February 15th, 2016, your pfring will be too old and this install will fail.

To install/upgrade ntopng:

	sudo soup
	
	(reboot if required)
	
	wget https://github.com/branchnetconsulting/so1404-ntopng-installer/raw/master/install_ntopng_on_so
	
	chmod 700 install_ntopng_on_so
  
	sudo ./install_ntopng_on_so
