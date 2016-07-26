# so1404-ntopng-installer
Script to install or upgrade to the latest stable ntopng from the official ntop repo, onto a Security Onion 14.04 sensor

The ntopng packages maintained at http://packages.ntop.org/ depend on the pfring package also maintained there.  However, Security Onion systems use a custom set of securityonion-pfring-* packages to satisfy pfring dependencies, and these cannot coexist with the pfring package from the ntop.org repo.  

This installer script fetches the needed content from the ntop repo, and then installs ntopng in a way that works cleanly on Security Onion sensors.

Requirement: You must be running a recently "soup"-updated version of Security Onion, either from the stable or testing repo.  Otherwise your version of pfring will be too old for ntopng to work.

To install/upgrade ntopng:

	sudo soup
	
	(reboot if required)
	
	wget https://github.com/branchnetconsulting/so1404-ntopng-installer/raw/master/install_ntopng_on_so
	
	chmod 700 install_ntopng_on_so
  
	sudo ./install_ntopng_on_so

Note that for new installs of ntopng, login authentication is enabled by default (starting username/password is admin/admin) and ntopng listens on tcp/3000 for https connections.  If you are running this installer on an SO system upgraded from 12.04 to 14.04 on which ntopng 1.2.X had been previously installed according to the Wiki article (https://github.com/Security-Onion-Solutions/security-onion/wiki/DeployingNtopng), then your original /etc/ntopng/ntopng.conf file will not be overwritten by this installer script.  Consider reviewing the settings in /etc/ntopng/ntopng.conf.dist and copying across any desired changes to /etc/ntopng/ntopng.conf.
