Test & Observe: Telnet to FSNA-SW1
*Telnet to FSNA-SW1 and observe the sniffer log to 
see clear text passing of credentials
1. NOC-PCàDesktopàCommand Prompt
2. C:\>telnet 192.168.100.251
3. Login to the switch
4. Access the Sniffer GUI tab
5. Observe the sniffer log to see each typed 
character being passed in clear text
Configure: Secure Shell on FSNA-SW1
1. (config)#ip domain name fsna.local
2. (config)#crypto key generate rsa
modulus: 2048
3. (config)#ip sshversion 2
*note –Packet Tracer does not actually perform 
encryption on the SSH traffic, so the sniffer will still 
show it as not encrypted
Test & Verify: Secure Shell on FSNA-SW1
1. NOC-PCàDesktopàCommand Prompt
2. C:\>ssh–l fsna 192.168.100.251
3. Login to the switch
4. #show sshàto view current sshsessions
Configure: Lock Down for No Telnet Access
1. (config)#line vty 0 15
2. (config-line)#transport input ssh
3. (config-line)#transport output ss# Connect-Hosts-to-LAN
