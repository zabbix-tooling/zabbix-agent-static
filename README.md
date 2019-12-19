zabbix-agent-static
=======================

Sometimes your need to install static binaries of zabbix:

- you run some legacy systems where you cannot install recent libaries</br>
  (legacy operation systems, legacy enterprise software, ...)
- there are no operating system packages for your plattform
- ...

This repository downloads archives for static agents and creates suitable packages.

Currently supported:

- Debian Packages
- RPM Packages (partially, sysv init not complete)

This project utilizes fpm:

  * Adpoted from: https://www.digitalocean.com/community/tutorials/how-to-use-fpm-to-easily-create-packages-in-multiple-formats
  * FPM https://fpm.readthedocs.io/en/latest/intro.html

# How to use


 * Install FPM
   ```
   sudo apt-get install ruby-dev build-essential debhelper devscripts rpm
   gem install fpm --user
   ```
 * Add a zabbix-agent config template, if neccessary (`<projectdir>/zabbix_agentd.conf.custom`)
 * Create packages
   ```
   git commit ....
   ./create_packages
   ```
 * Install the rpm or debian archive on as an addition to your zabbix-agent:
 
   ```
   rpm -Uvh noarch/zabbix-agent-static-<version>.noarch.rpm
   dpkg -i zabbix-agent-static_<version>_all.deb
   ```

# Licence and Authors

Additional authors are very welcome - just submit your patches as pull requests.

  * Marc Schoechlin <ms@256bit.org>
  * Marc Schoechlin <marc.schoechlin@vico-research.com>
 
This software is licensed by GPLv2 - review file "LICENSE"
