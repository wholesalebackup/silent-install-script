# Create a silent installation script

## Remotely deploy your backup service by pushing a silent installation

You can ‘push’ new silent installations of your branded [remote backup software](https://wholesalebackup.com/backup-software/)
 to your client’s computers which will use all default settings (including selections) as specified as default when you built your custom branded white label WholesaleBackup software client.

Requirements and Important Notes:

* .NET 4.0 must already have been installed or enabled on the client computer; unfortunately installing or enabling .NET 4.0 is manual process on some operating systems and sometimes requires a reboot so we can’t automate this for silent pushed installs. 
* The installation command must be run as an Administrator or Domain Administrator
Doing a silent install will skip credit card capture, if you specified it during your white label build, so no credit card information will be prompted for or sent to your backup server.
* The silent installer will still try and do a firewall test so that it can actually connect to your backup server to register and create the backup account. The client computer must be on the Internet in order to access your backup server and install the software. Furthermore, it is possible that client-side anti-malware software may block the software from accomplishing this test, in which case the installation will fail.
* The scheduling service will be installed as “Local System” so the default selections you specified in your white label build should not include any network shares, mapped drives, or other selections which the default “Local System” account does not have access to on the client computer. The Windows “Local System” account has access to all files/folders on the client computer by default (unless one manually removed privileges on specific folders/files) but it can never access network shares or mapped drives because of limitations that Microsoft imposes for security purposes. If you did not specify any default selections for your white label build, then the default parent directory for all user account data will be selected to backup for silent installs.
* At a minimum, you MUST specify the following mandatory command line parameters:

```
/SP- /VERYSILENT /NORESTART /WPUSH /WACCOUNT "account_name" /WPASS "password"
```

#### Optional Command Line Parameters:

These parameters correspond to those on the Account registration tab of the registration wizard and are described below:

/WFIRST "first name"

/WLAST "last name"

/WORG "organization name"

/WPHONE "(800) 555-1212 x123"

/WEMAIL "me@domain.com"

```
myBrand_installer.exe /SP- /VERYSILENT /NORESTART /WPUSH /WACCOUNT "VeryImpCinc" /WPASS "foo1Bar2s" /WORG "Very Important Customer, Inc."
```

#### Need help? 
Connect with [wholesalebackup.com](https://wholesalebackup.com/) if you have any questions.

