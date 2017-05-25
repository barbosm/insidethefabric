# Basic Management Configuration

First let's do some generic but very important management configuration.

> #### info::CLI Structure
>
> You'll most likely notice that the FortiOS \(the operating system that runs on FortiGates\) is a little different from let's say [VyOS](https://vyos.io/) or a Cisco Switch where you can configure things in one line, instead in FOS you need to enter or 'get in' the relevant config section, so the config will be nested inside that specific section. A good way to explore the options inside that section is to simply type '**tree**' which will give you all options inside that section or simply type **'?'** after a part of the command, it will give the options to complete the current command.

## Change admin password

```
config system admin
    edit "admin"
        set password verygoodandsecurepassword
    next
end
```

## Hostname

```
config system global
    set hostname FG
end
**[terminal]

FGVM020000000000 # [command] config system global
FGVM020000000000 (global) # [command] set hostname FG
FGVM020000000000 (global) # [command ]end
FG # 
```

## Admin session timeout

```
config system global
    set admintimeout 60
end
```

## Update firmware

> #### warning::Firmware Upgrade Procedure
>
> Always follow the [upgrade path](http://cookbook.fortinet.com/sysadmins-notebook/supported-upgrade-paths-fortios/) and read the release notes of the target version before updating the firmware.

First check your current version:

```
FG # get sys stat
Version: FortiGate-VM64 v5.4.2,build1100,161101 (GA)
...
**[terminal]
**[prompt FG]**[delimiter  # ]**[command get sys status]

**[prompt FG]**[delimiter  # ]**[command get sys stat]
**[warning Version: FortiGate-VM64 v5.4.2,build1100,161101 (GA)]
```

Now you can choose the target version, download it from the FortiGuard servers and update your device.

```
FG # exec restore image management-station ?
Image-ID    Version
05006000FIMG0012006000    v5.06 GA b1449 (upgrade)
05004000FIMG0012004004    v5.04 GA P4 b1117 (upgrade)
05002000FIMG0012002011    v5.02 GA P11 b0754 (downgrade)
05002000FIMG0012002010    v5.02 GA P10 b0742 (downgrade)
05000000FIMG0012000013    v5.00 GA P13 b0322 (downgrade)
05000000FIMG0012000012    v5.00 GA P12 b0318 (downgrade)
04000000FIMG0012003018    v4.00 MR3-GA P18 b0689 (downgrade)
04000000FIMG0012003016    v4.00 MR3-GA P16 b0686 (downgrade)

FG # exec restore image management-station 05004000FIMG0012004004
Please wait...

Getting image 05004000FIMG0012004004 from Management station...
#################################################################
This operation will replace the current firmware version!
Do you want to continue? (y/n)y


Checking new firmware integrity ... pass

Please wait for system to restart.
```

> #### Info::Firmware List
>
> You can also obtain the image list with the command "diag fdsm image-list", this can be useful in some scripting scenarios.

#### 

> #### warning::Troubleshooting Tip
>
> If you got something like this after trying to obtain the image from FortiGuard Distribution Network \(FDN\):
>
> ```
> Result=2
> Command fail. Return code 5
> ```
>
> Simply try again, this can mean some issue with your Internet link or the connection was refused for some random reason.

## Check licensing and security updates

After the update you can check the FortiGate entitlement \(which security services it has activated and have support, essentially this dictates if you can update AV, IPS, AC \(Application Control\) definitions.

```
FG # diag autoupdate versions 
AV Engine
---------
Version: 5.00239
Contract Expiry Date: n/a
Last Updated using manual update on Wed Nov 16 15:45:00 2016
Last Update Attempt: n/a
Result: Updates Installed

Virus Definitions
---------
Version: 46.00292
Contract Expiry Date: n/a
Last Updated using manual update on Sun Apr 23 05:10:00 2017
Last Update Attempt: n/a
Result: Updates Installed
```

## 

## You got mail!

You're proud of all the hard work done but there is still more to come, you just received a new email from your boss, this one contains the network diagram and ip addressing for your network.

```
**[terminal]
**[prompt foo@joe]**[path ~]**[delimiter  $ ]**[command ./myscript]
Normal output line. Nothing special here...
But...
You can add some colors. What about a warning message?
**[warning [WARNING] The color depends on the theme. Could look normal too]
What about an error message?
**[error [ERROR] This is not the error you are looking for]
```



