You can access the MiSTer through Samba network.

## Why Use Samba

With Samba you can work with remote files as quick as with local files, if you don't need the whole content.

Samba is the native protocol for Windows shares. MiSTer already has FTP and SSH services, but Samba has a special feature: Windows treats Samba shares as a local filesystem. 

For example, with FTP/SFTP,, if you want to view or edit a file, then you need to download it fully first. With Samba, only a small required portion of file will be loaded. If you are editing a large file of 100MB+, then it makes big difference. Similarly, if you want to use a HEX editor, you don't need to download the whole file. Just open the file in a HEX editor and only small portion will be loaded where you can quickly edit required bytes and save it back quickly. 

This means that with Samba access, you can mount VHD files on your PC without downloading them! Use a utility such as [ImDisk](https://sourceforge.net/projects/imdisk-toolkit/) to can mount VHD files as a local disk (mount it as removable store for easier un-mounting).

## Instructions:
* By default Samba service is not active. You need to rename **/media/fat/linux/_samba.sh** to **linux/samba.sh**, then edit this file if you need specific user name and password (default is user `root` with pass `1`) and then reboot the MiSTer.
* you can access the MiSTer either by IP address or by name `\\MiSTer` (or `\\mister` - case insensitive).
* This can also be accessed from S/FTP by using **IP address**, using your usual MiSter login (same as Linux terminal)

## Notes:
* Make sure you've closed all opened remote files and un-mounted all remote VHDs before restarting the MiSTer or start the cores using the same VHDs in order to prevent the data corruption!
* MiSTer's default samba workgroup is `MiSTer`. Usually you will not need this to log in.

## Adding USB drive as a Samba share

If you need to add any additional folders to Samba (eg for additional drives) you will need to ssh into the MiSTer device. Using your ssh client, connect to the MiSTer device using the default username and password. Then type the following command :-
```
nano /etc/samba/smb.conf
```

At the bottom of the file, add the following lines :-

```
[usb]
path = /media/usb0
public = yes
writeable = yes
printable = no
```
Press Ctrl+X and then Y to save, 
then at the command prompt, type 'reboot'

The MiSTer will now restart and the new share should be visible.

## Troubleshooting:
If you're using a Windows OS (Vista and above) while trying to access the share and the credentials do not work, there may be a possibility that the LAN Manager authentication level is not being worked out correctly between the Windows OS and the Samba daemon on MiSTer.

The error message may manifest itself as a **The specified network password is not correct** error. A fix is to lower the Samba NTLM authentication level on the MiSTer to NTLM v1.

This is done with the following steps:
1. SSH into your MiSTer instance.
2. Edit the Samba configuration file.
```
nano /etc/samba/smb.conf
```
3. Append under global, where the keyword **yes** signifies ntlmv1-permitted, which allows for NTLMv1 and above for all clients (against MiSTer). By default the value is not set explicitly and is **no**, which equates to ntlmv2-only. Further information is specified in the **ntlm auth (G)** section at [https://www.samba.org/samba/docs/current/man-html/smb.conf.5.html.](https://www.samba.org/samba/docs/current/man-html/smb.conf.5.html)
```
[global]
   min protocol = SMB2
   ntlm auth = yes
```
4. Reboot MiSTer or restart the Samba daemon.
```
/etc/init.d/S91smb restart
```
You should see no errors when manually restarting. e.g.
```
/root# /etc/init.d/S91smb restart
Shutting down SMB services: OK
Shutting down NMB services: OK
Starting SMB services: OK
Starting NMB services: OK
```
Alternatively, on the Windows OS, change the Windows registry HKLM\SYSTEM\CurrentControlSet\Control\Lsa\LMCompatibilityLevel to 3. Note that you may/may not have permission depending on your security policy or Administrator rights. This is described by Microsoft at [https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/network-security-lan-manager-authentication-level.](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/network-security-lan-manager-authentication-level)
