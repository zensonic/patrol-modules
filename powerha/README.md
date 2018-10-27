Modulesfor BMC Patrol that will monitor the state on a AIX powerha cluster. 

Features:

* Monitor node availability, through /usr/es/sbin/cluster/utilities/clshowsrv -v
* Monitor resource group availability, through  /usr/es/sbin/cluster/utilities/clRGinfo -s
* Monitor cluster status through /usr/es/sbin/cluster/utilities/clshowsrv -v
* Gets node topology through /usr/es/sbin/cluster/utilities/cltopinfo
* Updates UNIX.km filesystem filterlist for filesystems that are part of a ressource group based on /usr/es/sbin/cluster/utilities/cllsfs

Installation guide:

* copy the .km files to the patrol agents knowledge directory on all cluster nodes
* compile the .psl file into a .lib file with the command psl -l powerha.psl (if you want to cook your own .lib file)
* copy the .lib file to the patrol agents psl directory on all cluster nodes.
* grant permission for the patrol user to run the above cluster commands through sudo
* add pconfig variable "/POWERHA.activate" = { REPLACE = "1" }" to the patrol agent on all cluster nodes.
* load the POWERHA.km on all cluster nodes.

Usage:
* You can right click on the POWERHA class once it is loaded and toggle debugging.

Disclaimer:
These modules are by no mean in a form or shape that follows offical developer guidelines from BMC, as they

Do not have recoverable actions
Do not have help pages
Do not have nice and fancy patrol icons
On the other hand, they are

Free (under GPL V3)
Tested to catch critical events over quite some years.
If you need help in adding features send a mail to github@zensonic.dk and we can figure out what that will cost you.

Thomas
