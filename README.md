# Windows Fix

Simple powershell scripts to fix Windows 10.

Clone or directly download this repository and run `./00-SetExecutionPolicy-Unrestricted.ps1` first. Then run whatever **fix** you want for your system.

Instructions for some scripts is present [below](https://github.com/dpi0/win-fix#for-servicesdisable-windowsdefender-dependserviceps1).

To run a single script remotely without manually downloading, Use the `https://raw.githubusercontent.com` GitHub url for that script. Like,

```powershell
irm "https://raw.githubusercontent.com/dpi0/win-fix/refs/heads/main/Services/Disable-Multiple-Useless-Services.ps1" | iex
```

> [!TIP]
> Why do i need to run `./00-SetExecutionPolicy-Unrestricted.ps1` first?
> 
> 1. Lowers the execution policy for your user only.
> 2. `Unrestricted` policy tells windows - **Run everything, but warn me when running something downloaded.**
>
> Some scripts might fail (that fall under the default `Restricted` policy) and say *File cannot be loaded because running scripts is disabled on this system.*

## For `./Services/Disable-WindowsDefender-DependService.ps1`

<https://www.reddit.com/r/Windows10/comments/1hygqe1/comment/m6id128/?context=3>

1. Disable virus protection in Defender manually
2. Boot into safe mode, run `msconfig` in `win+r` then `Boot → Safe boot → Minimal`
3. Run this script in safe mode
4. Reboot normally, run `msconfig` in `win+r` then `Boot → uncheck Safe boot`

## For `./Services/Tweaks/Fix-SSH-PrivateKey-Permissions.ps1`

1. Update `$keyPath` variable to match your private key file path
2. Default `$keyPath` is `%USERPROFILE%\.ssh\id_rsa`

## For `./Services/Tweaks/Rename-Computer-And-Reboot.ps1`

1. Update `$newName` variable to set your new computer name
2. Default `$newName` is `windows`

## For `./Services/Tweaks/Set-StaticWiFi-IP.ps1`

0. Get your current variable values from the command `ipconfig /all`. Look specifically in the `Wireless LAN adapter Wi-Fi:` section at the bottom.
1. Update `$newIPAdress`, `$prefixLength` and `$gateway` variables
2. Default `$newIPAdress` is `192.168.1.60`
3. Default `$prefixLength` is `24`
4. Default `$gateway` is `192.168.1.1`
