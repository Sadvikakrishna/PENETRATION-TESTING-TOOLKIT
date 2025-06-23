# PENETRATION-TESTING-TOOLKIT

*COMPANY NAME* : CODTECH IT SOLUTIONS

*NAME*	       : PASUPULETI SADVIKA KRISHNA

*INTERN ID*	   : CT06DG3074

*DOMAIN*	     : CYBER SECURITY & EHICAL HACKING

*DURATION*	   : 6 WEEKS

*MENTOR*       : NEELA SANTOSH	

#The Description about the code

The provided code is a modular Penetration Testing Toolkit implemented in Python, designed to perform several basic cybersecurity tasks through a command-line interface. The  
main script (main.py) presents a menu-driven interface that allows users to select from five core functions: port scanning, SSH brute-forcing, banner grabbing, vulnerability  
checking, and WHOIS lookups. Each function is organized into its own module under the modules/ directory, enhancing code readability and maintainability. The port_scanner.py  
module scans the first 1024 ports of a target IP address to identify open ports using socket connections. The brute_forcer.py module attempts to brute-force SSH login        

credentials by iterating through a user-supplied password list, leveraging the Paramiko library for SSH connections. The banner_grabber.py module connects to a target         
(default port 80) and sends an HTTP HEAD request to retrieve and display the service banner, which may reveal software and version information. The vuln_checker.py module     
performs a simple keyword-based vulnerability check by matching strings like “php” or “wordpress” in the domain name, serving as a placeholder for integration with real       
vulnerability databases. Finally, the whois_lookup.py module uses the whois library to retrieve registration and ownership details for a given domain. This toolkit is         
intended for educational or internal testing purposes and provides a foundational framework that can be extended with more advanced features and integrations for real-world   
penetration testing.












