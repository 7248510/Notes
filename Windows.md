# Windows Notes
* Zip files fail to download with Internet Information Services Manager
  <br>To fix authentication 401 errors the fix is below
  <br>Right click the folder where your files are stored/site directory. > properties > security > edit > add
  <br>Enter the Anonymous users identity. In my case IUSR
  <br>Source is below
  <br>https://knowledge.broadcom.com/external/article/155008/anonymous-access-is-failing-401-errors-i.html
* Visual studio errors relating to Git & Git bash errors
  <br>Tweak Exploit Protection in Windows 10
  <br>Below is the thread that fixed my problem. Thanks Gamitech
  <br>You can either turn off "Force randomization for images(Mandatory ASLR)" Or follow the steps below
  <br>In my tweaking Mandatory ASLR fixed my problem, I didn't need to change Bottom-up ASLR(which is on by default).
  <br>https://github.com/git/git-scm.com/issues/1081
  
* Rearming windows server 19
  <br>https://sid-500.com/2017/08/08/windows-server-2016-evaluation-how-to-extend-the-trial-period/
  <br>slmgr -dlv = seeing status
  <br>slmgr -rearm = reboot Windows Server to get an extra 180, you can do this up to six times.
  <br>After your evaluations up you'll have 10 additional days with the OS.
  
* Ethernet adapter
<br>Problem: Having to renable your(my) ethernet adapter to reach my servers. <br>Solution: Disable/uncheck allow device('s) to save power.The tab is in the device managers power management tab.
<br>https://answers.microsoft.com/en-us/windows/forum/windows_10-networking/why-do-i-have-to-reset-my-ethernet-adapter-daily/32669e92-2211-46fe-a823-ac121212a99c
<br>Device manager > Ethernet adapter > power management.
