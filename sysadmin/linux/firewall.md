# firewall

* Allow the default HTTP and HTTPS port, ports 80 and 443, through firewalld:

  `sudo firewall-cmd --permanent --add-port=80/tcp` `sudo firewall-cmd --permanent --add-port=443/tcp`

  And reload the firewall:

  `sudo firewall-cmd --reload`

