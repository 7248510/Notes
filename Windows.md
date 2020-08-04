# Windows Notes
* Zip files fail to download with Internet Information Services Manager
  <br>To fix authentication 401 errors the fix is below
  <br>Right click the folder where your files are stored/site directory. > properties > security > edit > add
  <br>Enter the Anonymous users identity. In my case IUSR
  <br>Source is below
  <br>https://knowledge.broadcom.com/external/article/155008/anonymous-access-is-failing-401-errors-i.html
