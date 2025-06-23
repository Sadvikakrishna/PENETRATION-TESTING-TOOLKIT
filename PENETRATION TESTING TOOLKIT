### main.py
from modules import port_scanner, brute_forcer, banner_grabber, vuln_checker, whois_lookup
def main():
    print("Penetration Testing Toolkit")
    print("1. Port Scanner")
    print("2. SSH Brute Forcer")
    print("3. Banner Grabber")
    print("4. Vulnerability Checker")
    print("5. Whois Lookup")
    choice = input("Enter your choice: ")
    if choice == "1":
        target = input("Enter target IP: ")
        port_scanner.scan(target)
    elif choice == "2":
        host = input("Enter host IP: ")
        brute_forcer.ssh_brute_force(host)
    elif choice == "3":
        target = input("Enter target IP: ")
        banner_grabber.grab_banner(target)
    elif choice == "4":
        domain = input("Enter domain: ")
        vuln_checker.check(domain)
    elif choice == "5":
        domain = input("Enter domain: ")
        whois_lookup.lookup(domain)
    else:
        print("Invalid choice")
if __name__ == "__main__":
    main()
### modules/port_scanner.py
import socket
def scan(target):
    print(f"Scanning {target}...")
    for port in range(1, 1025):
        try:
            sock = socket.socket()
            sock.settimeout(0.5)
            sock.connect((target, port))
            print(f"Port {port} is OPEN")
            sock.close()
        except:
            pass
### modules/brute_forcer.py
import paramiko
def ssh_brute_force(host):
    username = input("Enter SSH username: ")
    wordlist = input("Enter path to password list: ")
    with open(wordlist, 'r') as file:
        for line in file:
            password = line.strip()
            try:
                ssh = paramiko.SSHClient()
                ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())
                ssh.connect(host, username=username, password=password, timeout=3)
                print(f"[+] Password found: {password}")
                ssh.close()
                return
            except:
                print(f"[-] Failed: {password}")
    print("[-] Password not found.")
### modules/banner_grabber.py
import socket
def grab_banner(target, port=80):
    try:
        sock = socket.socket()
        sock.connect((target, port))
        sock.send(b"HEAD / HTTP/1.0\r\n\r\n")
        banner = sock.recv(1024)
        print("Banner:")
        print(banner.decode().strip())
        sock.close()
    except Exception as e:
        print(f"Error grabbing banner: {e}")
### modules/vuln_checker.py
import requests
def check(domain):
    print(f"Checking vulnerabilities for {domain}...")
    keywords = ["php", "wordpress", "apache"]
    for keyword in keywords:
        if keyword in domain:
            print(f"Possible vulnerability related to {keyword}. Check CVE database.")
            return
    print("No known issues detected. For real use, integrate with NVD or Vulners API.")
### modules/whois_lookup.py
import whois
def lookup(domain):
    try:
        info = whois.whois(domain)
        print(info)
    except Exception as e:
        print(f"WHOIS lookup failed: {e}")
