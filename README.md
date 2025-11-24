# Windows Cleanup
## For `./Services/Disable-WindowsDefender-DependService.ps1`

<https://www.reddit.com/r/Windows10/comments/1hygqe1/comment/m6id128/?context=3>

1. Disable virus protection in Defender manually
2. Boot into safe mode, run `msconfig` in `win+r` then `Boot → Safe boot → Minimal`
3. Run this script in safe mode
4. Reboot normally, run `msconfig` in `win+r` then `Boot → uncheck Safe boot`
