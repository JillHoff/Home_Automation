# Download the most current Raspberry Pi Image (minimul image - No desktop needed)
* download from the [Raspbian image page](https://www.raspberrypi.org/downloads/raspbian/)
* [direct image link](https://downloads.raspberrypi.org/raspbian_lite_latest)
* Extract the image into a folder

# Download balena Etcher
  * Download from [Here](https://www.balena.io/etcher/)
  * Run installer to install on your system

#B uild SD Card for Raspberry Pi
  ##Install rasbian onto an SD card
* insert SD Card into computer
* run Etcher:
    * Select image from above
    * Select SD card from above
    * choose "Flash" and wiat for installation to finish.
    
# Enable SSH by default:
* Once installation is complete (onto the SD card) open the SSD cards file system.
* On the root partition of the SD card create a file named ssh (no file extention) on the root of the filesystem
  
# Enable Wifi (so pi boots headless - monitor, keyboard, and Mouse is never needed directly on the pi)
* on the root partion of the SD card create a file called wpa_supplicant.conf
  Enter the following Text (replace your wifi info and country code) into the wpa_supplicant.conf and save the file
  
'''
    country=US
    ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
    update_config=1

    network={
        ssid="NETWORK-NAME"
        psk="NETWORK-PASSWORD"
    }
''''
 
Move the SD card to the Pi and plug it in, wait 2 minutes

Find the devices IP address on your network, and use that to ssh to the pi.  
    On Windows that would be ssh pi@<IP_Address> (pi is the default username, once you create other users you would use those instead of pi)
    accept the security warning by typing 'yes'
    enter the password (default password is 'raspraspberry') 

Once logged on enter the command 'raspi-config' to set basic configuration parameters (you can do this through command line and file edits, but this is easy)
  Minimum suggested changes:
    1. option 1 -> Change User Password (everyone knows the default)
    2. Option 2 -> Network Options -> N1 Change Host Name (becasue you want it to be a bit descriptive)
  change any other optioin you need....click finish and reboot
  
 Logback on with new password:
 update OS
      run sudo apt-get update
      run sudo apt-get upgrade -y
      wiat a long time for this to finish

      
 
    
    
    

 
  

