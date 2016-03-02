dnssinkholelist
========
dnssinkholelist is a python package focused on combining open source lists of malicious domains, dynamic dns domains, and advertisement domains for use in a dns sinkhole on a bind server or /etc/hosts file.


Please Note
===========
* This is a script I used for a while for a bind server--- a lot needs cleaned up before you use it automatically to feed into bind or /etc/hosts. Consider it a work in progress.
However, you can use it for a unique list of malicious/sinkhole domains from below.
* Requires internet access for downloading domain lists listed below.


Requirements
============
* Python 2.7
* pip install -U requests[security] #Install requests security
* pip install -U beautifulsoup; #For HTML Parsing
* pip install -U pyyaml; #For Config Parsing


Install
=======
pip install -e git+https://github.com/neu5ron/dnssinkholelist@master#egg=dnssinkholelist


Malware Lists
==============
- [x] https://pgl.yoyo.org/adservers/serverlist.php?hostformat=;showintro=0
- [x] http://mirror1.malwaredomains.com/files/justdomains / https://mirror.cedia.org.ec/malwaredomains/justdomains
- [x] https://www.malwaredomainlist.com/hostslist/hosts.txt
- [x] https://zeustracker.abuse.ch/blocklist.php?download=domainblocklist
- [x] https://palevotracker.abuse.ch/blocklists.php?download=domainblocklist
- [x] https://feodotracker.abuse.ch/blocklist/?download=domainblocklist
- [x] https://isc.sans.edu/feeds/suspiciousdomains_Low.txt
- [x] https://isc.sans.edu/feeds/suspiciousdomains_Medium.txt
- [x] https://isc.sans.edu/feeds/suspiciousdomains_High.txt
- [x] https://malc0de.com/bl/ZONES
- [x] http://labs.sucuri.net/malware-data
- [x] http://cybercrime-tracker.net/all.php
- [x] http://malwareurls.joxeankoret.com/normal.txt
- [x] https://gist.githubusercontent.com/neu5ron/8dd695d4cb26b6dcd997/raw/5c31ae47887abbff76461e11a3733f26bddd5d44/dynamic-dns.txt
- [x] http://hosts-file.net/download/hosts.txt #Might be too many false positives
- [x] http://vxvault.net//URL_List.php
- [x] http://malwaredb.malekal.com/export.php?type=url
- [x] http://support.it-mate.co.uk/downloads/HOSTS.txt #Might be too many false positives
- [x] https://data.phishtank.com/data/online-valid.json


Additional lists not implemented
==============

* http://www.malwarepatrol.net/cgi/submit?action=list_bind #Requires Signing Up
* http://mtc.sri.com/live_data/malware_dns/ #Not working
* http://exposure.iseclab.org/malware_domains.txt #Not working
* https://spyeyetracker.abuse.ch/blocklist.php?download=domainblocklist #Discontinued
* https://threatfeed.nullsecure.org/ #TOOOOOOOOO Late to the party? No updates in 2016 as of 2016-02-18.


TODO List
==============
- [ ] Use python os commands for error checking and such
- [ ] Test if bind directories exist and if not create them etc
- [ ] Add variables for where bind files should be stored, like /use/share/bind folder thing
- [ ] If anything returns no values then email or alert/log
- [ ] Implement WhiteList via  a gist/github link that is auto updated like the other lists/feeds
- [ ] Ability to choose between creating a host file or bind file..if bind then only get lowest level domain. if host file then keep as is
- [ ] Use python logging instead of print and such
- [ ] Option to exclude some whitelist / make it a yaml?
- [ ] Make unique/sorted domains into a function as a new one is added in the corresponding lists function... instead of at the end
- [ ] Number each list, and add ability to disable list via the command line by specifying something like --disable-lists=1,2,3,4,5
- [ ] CLI Options
