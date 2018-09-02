# so-ntopng-installer
Script to install or upgrade to the latest stable ntopng from the official ntop repo, onto a Security Onion sensor running Ubuntu 14.04 or 16.04

The ntopng packages maintained at http://packages.ntop.org/ depend on the pfring package also maintained there.  However, Security Onion systems use a custom set of securityonion-pfring-* packages to satisfy pfring dependencies, and these cannot coexist with the pfring package from the ntop.org repo.  

This installer script fetches the needed content from the ntop repo, and then installs ntopng in a way that works cleanly on Security Onion sensors.

Requirement: You must be running a recently "soup"-updated version of Security Onion, either from the stable or testing repo.  Otherwise your version of pfring may be too old for ntopng to work.

To install/upgrade ntopng on Security Onion on Ubuntu 14.04:

	sudo soup
	(reboot if required)
	rm -f install_ntopng_on_so_14
	wget --no-check-certificate https://github.com/branchnetconsulting/so-ntopng-installer/raw/master/install_ntopng_on_so_14
	chmod 700 install_ntopng_on_so_14
	sudo ./install_ntopng_on_so_14

To install/upgrade ntopng on Security Onion on Ubuntu 16.04:

	sudo soup
	(reboot if required)
	rm -f install_ntopng_on_so_16
	wget --no-check-certificate https://github.com/branchnetconsulting/so-ntopng-installer/raw/master/install_ntopng_on_so_16
	chmod 700 install_ntopng_on_so_16
	sudo ./install_ntopng_on_so_16

Note that for new installs of ntopng, login authentication is enabled by default (starting username/password is admin/admin) and ntopng listens on tcp/3000 for https connections.  Consider reviewing the settings in /etc/ntopng/ntopng.conf.dist and copying across any desired changes to /etc/ntopng/ntopng.conf.
