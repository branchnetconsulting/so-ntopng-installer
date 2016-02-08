# so1404-ntopng-installer
Script to install or upgrade to the latest stable ntopng from the official ntop repo, onto a Security Onion 14.04 sensor

The ntopng packages maintained at http://packages.ntop.org/ depend on the pfring package also maintained there.  However, Security Onion systems use a custom set of securityonion-pfring-* packages to satisfy pfring dependencies, and these cannot coexist with the pfring package from the ntop.org repo.  

This installer script fetches the needed content from the ntop repo, and then installs ntopng in a way that works cleanly on Security Onion sensors.

To run the installer:
  wget https://github.com/branchnetconsulting/so1404-ntopng-installer/raw/master/install_ntopng_on_so
  sudo bash -c "source ./install_ntopng_on_so"

Requirement: Security Onion sensor running on Ubuntu 14.04 with a pfring version of 6.2.0 or higher.

As of Feb 8 2016, only the securityonion "test" repo has a current enough version of pfring to work with this installer script.
If you are member of security-onion-testing, see this thread related to the pfring 6.2.0 update to Security Onion:
https://groups.google.com/d/msg/security-onion-testing/_neNi0zcmlw/toug_WXdCAAJ
