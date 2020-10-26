
# AtomJump Messaging Appliance

Download VirtualBox for your platform (Windows / Linux / Mac), and the Messaging Appliance. Alternatively, for cloud users, you can import this file into your cloud system, once it is unzipped (see 'Importing Into Cloud Systems', below).

* https://www.virtualbox.org/wiki/Downloads
* https://frontcdn.atomjump.com/atomjump-live-wiki-0.7.6.zip
* [alternative source] https://atomjump-frontcdn-sng.sgp1.cdn.digitaloceanspaces.com/atomjump-live-wiki-0.7.6.zip


Unzip the Appliance file, which should create a .vmdk file. (On a Mac, you will need to use the 'Unarchiver' app since it is a larger file than the native Mac Unzipper can handle). 

Run VirtualBox on your platform, and add a 'New' project.
Enter:
```
Type = Linux
Version = Debian (64-bit)
```

Note: on Windows, if you can only see ‘Debian (32-bit)’ and you are definitely on a 64-bit machine, you will need to configure your server’s BIOS setting for virtualization to be switched on. See details here.

Click 'Continue' and then ‘Use an existing virtual hard disk drive’. Select the .vmdk file from your drive.
Run the VM and when you see a login after 20 seconds or so, enter the

```
Username: aj_customer
Password: lander5321
```

Once logged in, you should first change your password. Enter the line:
passwd
and enter your old and new passwords.

Then enter the line:
```
hostname -I
```
It should show you the VM server's IP address e.g. 10.0.2.15

Then enter 'Settings' for this Virtual Machine.
Go into 'Network' and click 'Port Forwarding'.
And add a new line similar to the above, using the Guest IP as the IP address found from the 'hostname -I' command.

Typical settings are:
```
Protocol: TCP
Host IP: 127.0.0.1
Host Port: 5100
Guest IP: 10.0.2.15 (or the IP address found after running 'hostname -I' within the server)
Guest Port: 80
```

The LiveWiki should now be accessible within a browser on http://127.0.0.1:5100	
You should click the ‘Update the server config’ link on this page, go back, and click through to the LiveWiki.

The main appliance target page is http://127.0.0.1:5100/livewiki/

Important Note: the first user to be created on the system will become the admin user, with admin rights to enter passwords on a particular forum. So, before you type anything in a messaging pop-up, go to ‘Settings’ in the popup, and enter your email and password.

If you are using the AtomJump Messaging app, and you want notifications on your phone:

Your phone should be connected to the same company Wifi or VPN network as the server. The address to use under the 'Private Server' link, or the 'Pair with a Private Server' address on the app homepage, is:

```
http://[your server IP or host]:5100/vendor/atomjump/loop-server/
```

E.g.
```
http://192.168.1.10:5100/vendor/atomjump/loop-server/
or
http://myhostname:5100/vendor/atomjump/loop-server/
```

Note: This is the same address to use if you want other server software to connect to your local AtomJump Server. If this connecting software is residing on the same machine, you can use the local server IP, also i.e.

```
http://127.0.0.1:5100/vendor/atomjump/loop-server/
```

## Technical Specifications

* __Operating System__ 	Debian Linux 64-bit, but runs on a host Windows Desktop, Windows Server, Mac OS X, Linux.
* __Software Language__ 	PHP 7.1
* __Database__ 	MySQL 5.7
* __Host Disk Space Required__ 	10GB
* __RAM Required__ 	1GB minumum
* __Simultaneous Users__ 	1 up to an approx maximum of 100, depending on usage patterns
* __Application Software__	AtomJump Messaging Server 2.6.7
* __Client Software__  Mobile browsers (e.g. iPhone or Android) / Desktop browsers (incl. Chrome / Firefox / Safari / Edge /IE). Optional AtomJump Messaging app for mobile notifications.
* __Default Plugins__ 	Large Stickers, App Notifications, Basic Emoticons, Language Switcher (English and Spanish included), Immediate Auto-Responder
* __Default Interface__ 	LiveWiki
* __Access__ 	Super-user file-level access, Database access on request, AtomJump support access.
* __Support__ 	US$ 64 (NZ$100) for TeamViewer-based remote access, plus prices for individual tasks (see the LiveWiki add-ons)
* __Price__ 	Free
* __Number of messages__ 	Approx 10 million under standard disk space
* __Number of shared images__ 	Approx 50,000 under standard disk space
* __Software Updates__ 	Manual, Debian OS updates. Application updates can be done by Support.
* __Security__ 	The software should be run within an internal intranet, for any secure applications. A secure https server can also be used, although it needs an individual key installation.


## Configuration
Log in, and enter the command:
```
sudo nano /jet/www/default/vendor/atomjump/loop-server/config/config.json
```

You can scroll down with the arrow keys. Under the "email" section, you can enter a configuration for sending off email notifications. Please see the User Guide for more details.

Once you have changed the file, you can hit 'Ctrl - O' together, then push 'Return'. It should say 'Wrote xx lines'. Push 'Ctrl - X' when done.

Warning: changes to the configuration files can make your system in-operable. We recommend backing up the file beforehand with e.g.

```
sudo cp /jet/www/default/vendor/atomjump/loop-server/config/config.json /jet/www/default/vendor/atomjump/loop-server/config/config-backup.json
```

## Software Updates
We recommend bringing your system up-to-date immediately after installation, and then at regular intervals (e.g. monthly) after that. This is particularly important if this instance is visible over the internet, as opposed to a local intranet installation.

Log in and enter the commands:

```
sudo apt-get update; sudo apt-get upgrade
```


We also recommend updating your core Messaging Server software  immediately after installation, and then at regular intervals (e.g. monthly) after that. This is particularly important if this instance is visible over the internet, as opposed to a local intranet installation. It will also fix some known issues (as listed below).

Log in and enter the command:

```
eval "$(curl -fsSL -H 'Cache-Control: no-cache' https://raw.githubusercontent.com/atomjump/live-wiki-updates/master/update)"
```

Then, click the following link to run a one-time update of your database:
http://127.0.0.1:5100/vendor/atomjump/loop-server/update-indexes.php
 
[or using your own IP address at http://myipaddress:5100/vendor/atomjump/loop-server/update-indexes.php]



## Notifications
By default, your Appliance will notify you if you are subscribed to a forum via your email.
In order to get popup-notifications to your Android or iPhones from your Messaging Appliance, you will need to add your 'push notification' certificate keys from Google and Apple.

__For Android:__
Create a Firebase project on Google.
Go to https://console.firebase.google.com/project/(your-project-id)/settings/cloudmessaging
You can find the API KEY in: (gear-next-to-project-name) > Project Settings > Cloud Messaging Server Key is the API key.

Then log in to your server,

```
sudo nano /jet/www/default/vendor/atomjump/loop-server/plugins/notifications/config/config.json
```

Please see the 'Configuration' instructions above for details on entering your keys.

__For iPhones:__
These instructions may help getting a key from Apple, but you can also try searching the internet for 'Apple push notification certificates'.

Once you have your .pem file, log in to your server,

```
sudo nano /jet/www/default/vendor/atomjump/loop-server/plugins/notifications/pushcert.pem
```

and write in your file.

Note: you can see a sample certficate file with:

```
sudo nano /jet/www/default/vendor/atomjump/loop-server/plugins/notifications/pushcertSAMPLE.pem
```

## Importing Into Cloud Systems

These instructions may change over time, depending on the particular cloud provider. The AtomJump Messaging appliance is a .vdmk file (once it is unzipped).

AWS   https://aws.amazon.com/ec2/vm-import/
Google   https://cloud.google.com/compute/docs/import/importing-virtual-disks
Microsoft Azure   https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwj-oPHg9cbsAhXXbX0KHcz7A9gQFjADegQIExAC&url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fazure%2Fvirtual-machines%2Fwindows%2Fprepare-for-upload-vhd-image&usg=AOvVaw15_gAzV7euEtgaNceUOUmC
DigitalOcean   https://www.digitalocean.com/blog/custom-images/?
IBM Cloud   https://cloud.ibm.com/docs/image-templates?topic=image-templates-preparing-and-importing-images
Oracle Cloud   https://blogs.oracle.com/cloud-infrastructure/import-a-vmware-virtual-machine-to-oracle-cloud-infrastructure
Alibaba Cloud   https://www.alibabacloud.com/help/doc-detail/127285.htm?spm=a2c63.p38356.b99.223.3b792ff1TyM2Ji

Note: AtomJump has no affiliation with any of these providers.

You are welcome to let us know if you manage to successfully import an AtomJump Messaging .vdmk, or not, with your provider.  https://atomjump.com/wp/contact/


## Known Issues
1. On an Android phone, if you are using a private IP address for your server, and your phone browser's setting's 'Lite Mode' is switched on, you may find images seem to flicker every 5 seconds or so.

We would recommend switching 'Lite Mode' off to stop the flickering.
Alternatively, once you associate a domain with the server, the problem usually disappears.

2. You cannot use ampersands '&' in the title of a forum. Please use an alternative.

3. Versions prior to 0.6.1 have a known security issue, so we strongly recommend using versions >= 0.6.1

4. Vertically oriented images might be blurry. Please see 'Software Updates' above, and run an update on the Messaging Server software to resolve this issue.


## Prior Versions

* https://frontcdn.atomjump.com/atomjump-live-wiki-0.7.5.zip
* https://frontcdn.atomjump.com/atomjump-live-wiki-0.7.4.zip
* https://frontcdn.atomjump.com/atomjump-live-wiki-0.7.3.zip
* https://frontcdn.atomjump.com/atomjump-live-wiki-0.7.2.zip
* https://frontcdn.atomjump.com/atomjump-live-wiki-0.7.1.zip
* https://frontcdn.atomjump.com/atomjump-live-wiki-0.7.0.zip

