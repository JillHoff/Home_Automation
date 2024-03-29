# Build Raspian SD with Wi-Fi and SSH enabled


## Download the most current Raspberry Pi Image (minimal image - No desktop needed)
* Download from the [Raspbian image page](https://www.raspberrypi.org/downloads/raspbian/)
* [Direct image link](https://downloads.raspberrypi.org/raspbian_lite_latest)
* Extract the image into a folder


## Download balena Etcher
  * Download from [Here](https://www.balena.io/etcher/)
  * Run installer to install on your system


## Build SD Card for Raspberry Pi
* Insert SD Card into computer
* Run Etcher:
    * Select image from above
    * Select SD card from above
    * Choose "Flash" and wait for installation to finish.
    * Wait for build to complete


## Enable SSH by default:

* Open the SSD cards file system.
* On the root partition of the SD card create a file named ssh (no file extention) on the root of the filesystem


## Enable Wifi

* On the root partion of the SD card create a file called wpa_supplicant.conf
  Enter the following Text (replace your wifi info and country code) into the wpa_supplicant.conf and save the file
  
```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
        ssid="NETWORK-NAME"
        psk="NETWORK-PASSWORD"
    }
```
 

# Boot, Login, and finish Configuration

## boot and login for the first time

* Move the SD card to the Pi and plug it in, wait 2 minutes
* Find the devices IP address on your network
* Use IP to ssh to the pi.  
  * On Windows that would be ssh pi@<IP_Address> 
* Login in
   * accept the security warning by typing 'yes' (should only have to do this the first time)
   * Default password is 'raspberry'
   
## finish Configuration

* Once logged on enter the command 'raspi-config'
  * Minimum suggested changes:
    * option 1 -> Change User Password (everyone knows the default)
    * Option 2 -> Network Options -> N1 Change Host Name (becasue you want it to be a bit descriptive)
  * Change any other optioin you need....click finish and reboot
  
## Upgrade OS to latest patches

* Logback on with new password
* Update OS
  * Run 'sudo apt-get update'
  * Run 'sudo apt-get upgrade -y'
  * Wait a long time for this to finish
  * Reboot 'sudo reboot'

      
 
    
    
    

 
  


