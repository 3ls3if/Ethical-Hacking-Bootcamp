 # Run Nmap

→ See the help menu using  nmap --help

		-> scan the metasploitable with a basic nmap scan
				
					nmap 192.168.10.4
					
		-> scan a range of IP address
				
				must know the subnet of network
				
							nmap 192.168.10.1/24
# Different Nmap Scans
→ TCP SYN scan
		
			sudo nmap -sS 192.168.10.4

 NOTE: The TCP SYN scan never establishes a full scan
 
 
→ TCP connect scan
 			
 			nmap -sT 192.168.10.4
 

→ UDP scan
	
			sudo nmap -sU 192.168.10.4     <- It takes time to complete the scan
			
			
→ ICMP sweep

		sudo nmap -PE 192.168.10.4
		

→ Stop scanning of ports 

	    sudo nmap -PE -sn 192.168.10.4   <- Only displays the host is up or not
	
	
→ Why nmap is reporting the host is up or not

		sudo nmap -PE -sn 192.168.10.4 --reason   <-Host is up, received arp-response
		
		
→ Check the Packets 

		sudo namp -PE -sn 192.168.10.4 --reson --packet-trace
		

→ ICMP sweep

		sudo namp -PE -sn 192.168.10.4 --reason --packet-trace --disable-arp-ping
	
	
	
→ performing scan on windows XP    //turn off the firewall

		sudo namp -PE -sn 192.168.10.5 --reson --packet-trace --disable-arp-ping 
		


→ -p option 

	The -p option will scan the given port numbers only

	-> nmap -p 80 192.168.10.4
	
	-> nmap -p 80,22,100 192.168.10.4
	
	-> nmap -p 1-100 192.168.10.4  
	
	-> nmap -p 1-65535 192.168.10.4
	
	
	
→ -F option

	The -F option scans first most usefull 100 ports
	
		->sudo nmap -F 192.168.10.4
		
		
→ -b option

	The -b option is for ftp bounce scan . We can check if the target is having any anonymous ftp sever
	
		-> nmap -b 192.168.10.4 192.168.10.3
		
		Default Username: anonymous
		
		Default Password: wwwftp@
		
		-> nmap -b -v user:user@192.168.10.4 192.168.10.3
		
		
→ -v option

	The -v option is for verbose output
	
	
	
→ -r option

	The -r option turn off randomization of port scanning
	
		-> sudo nmap -r 192.168.10.4 --reason --packet-tarce --disable-arp-ping

# Host Discovery
→ Host Discovery using ICMP Non-Echo Sweep


→ PP option

		sudo nmap -PP -sn 192.168.10.4 --reason --packet-trace --disable-arp-ping   <- sends Timestamp request
		 

→ PM option
		
		sudo namp -PM -sn 192.168.10.4 --reson --packet-trace --disable-arp-ping   <- Sends  Address Mask request
		
		
		
		
		

→ Host Discovery using TCP Sweep


→ PS option
	
		sudo nmap -PS 192.168.10.4 --reason --packet-trace --disable-arp-ping
		

→ PA option

		sudo nmap -PA 192.168.10.4 --reason --packet-trace --disable-arp-ping
		
		
		
		
		

→ Host Discovery using UDP Sweep


→ PU option

		nmap -PU -sn 192.168.10.4 --reason --packet-trace --disable-arp-ping

# OS Discovery
→ Discovering Target OS

	-> sudo nmap -O 192.168.10.4


→ Detecting Version of Service Running	

	-> sudo nmap -sV 192.168.10.4
	
	-> sudo nmap -sV --version-intensity 9 192.168.10.4    // By default the --version-intensity will be 7
	
→ -A Option  

	
	-> -A stands for aggressive scan
	
	        -> sudo nmap -A 192.168.10.4
	
# Save Nmap Output to a File
→ How to save the nmap scan results in a file


	-> sudo nmap -sS 192.168.10.4 >> output.txt
	
	
→ -oN option

	-> sudo nmap -oN output2 -sS 192.168.10.4 
	

# Bypass Firewall

→ Firewall is unpredictable


→ -f option
	
	The -f option fragment the packets into smaller packets
	
	-> sudo nmap -f 192.168.10.4    
	
	
 
→ -D option


	Hides your IP address by using decoys

		
	-> sudo nmap -D  RND: 5 192.168.10.4   // RND:5 option will generates 5 random IP addresses
	

→ Hide The local IP address


	-> sudo nmap -D 192.168.10.2,192.168.10.15,192.168.10.20,192.168.10.45,ME 192.168.10.4

				// ME is for the attacking machine IP address
	
# Security Evasion
→ -S option

	The -S option is used to spoof your IP address
	
          -> sudo nmap -S 8.8.8.8 -Pn -e eth0 -g 7777
          

→ See the Nmap manual for more
	
	
→ -Pn option
	
	The -Pn option assumes the host is up and scans the ports only
	
		->sudo nmap -Pn --open 192.168.10.4
	
