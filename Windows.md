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
  
