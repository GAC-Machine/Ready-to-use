### COMMAND(S) > USE > NOTE

#### Model [PH > PH > PH]

----

> for %a in (%pathext%) do where *%a

USE will list executables, batch and scripts accessible through the PATH env, this will include the default PATH entry, so just ignore those, it also can't tell whether an executable will launch GUI or completely CLI, but should be good enough to start.

NOTE See this post on Reddit https://www.reddit.com/r/techsupport/comments/1jteyx9/comment/mltqlz4/

----

> Get-ItemProperty HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\*, HKLM:\Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\*, HKCU:\Software\Microsoft\Windows\CurrentVersion\Uninstall\* |Select-Object DisplayName, DisplayVersion, Publisher, Size, InstallDate | Format-Table -AutoSize > C:\Users\USERNAME\Desktop\software.txt

USE print installed programs list

NOTE Command to run on Powershall

----

> adb devices
> adb shell cmd package list packages   

USE print installed apps in temrinal.

NOTE Commands to run on adb (Android Debug Bridge). 

[accpet promp regardinf computer's RSA fingerprint, the one using adb from]

----

[WINDOWS]
> $env:TOKEN  = "token here"
>
> $headers = @{
>    Authorization = "token $env:TOKEN"
>    Accept        = "application/vnd.github.v3+json"
>}
>
>$body = @{ last_read_at = "2026-05-31T00:00:00Z" } | ConvertTo-Json -Compress
>
>Invoke-RestMethod -Method PUT `
>    -Uri "https://api.github.com/notifications" `
>    -Headers $headers `
>    -Body $body `
>    -ContentType "application/json"

[LINUX]
> TOKEN="token_goes_here"; curl -X PUT -H "Accept: application/vnd.github.v3+json" -H "Authorization: token $TOKEN" https://api.github.com/notifications -d '{"last_read_at":"2026-05-31T00:00:00Z"}'

USE 1. If you do get a ghost notification just open a bash window or powershell ise and use these methods to clear it.
    2. You can make a temporary token here: https://github.com/settings/tokens/new
    3. Create a token that will expire tomorrow, look for the notifications checkbox and click that, no other tick boxes are required.
    4. After creating the token, grab the token and replace token_goes_here with your token, keep the quotes.

NOTE Linux shell with Linux Curl.

NOTE Windows users can do this: copy this and paste into Windows PowerShell ISE, then press the run button. Most Windows machine should have this, if not, just open up notepad (or any editor), paste the contents in, replace token here with your token, save the file as clearnotifs.ps1 or anything you like but must have .ps1 extension, then you can run from powershell with .\clearnotifs.ps1 in the current directory of the file.

NOTE After you can confirm the notif is gone, vaporize the token.
     For those who find this in the future and if the api is still the same, replace 2026 with the year after the current year. 2026>2027>2028>so on

Reference [Reddit](https://www.reddit.com/r/github/comments/1npc0kw/in_recent_phishing_wave_a_ton_of_people_will_have/)

----

> sudo systemctl start NetworkManager.service

USE Start service that manage network, fundamental for wifi to work correctly.  

NOTE Use in a terminal (used for Fedora 42 KDE Plasma Edition)

-----

> sudo systemctl start NetworkManager.service

USE Launch service that manage network, eg Wi-Fi

> sudo systemctl kill NetworkManager.service

USE End service that manage network, eg Wi-Fi

----




-----


> >  >




























































































































































