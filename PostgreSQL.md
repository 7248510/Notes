## PostgreSQL notes
### These steps use Webadmin4
# Add your binary path
1. File
2. Preferences
3. Paths -> Binary paths
4. Scroll down to your version
5. Enter/navigate "C:\Program Files\PostgreSQL\14\bin"
6. Save


# Back up
1. Click Servers(#)
2. Right click PostgreSQL #
3. Backup Server
4. Select your options
5. The backup is located in the documents folder of the current user

# To allow remote connections
## I recommend assigning privileges instead of allowing remote root. 
1. Know your IP ranges CIDR notation/Use a free tool to calculate the range
2. Navigate to the following path "C:\Program Files\PostgreSQL\14\data"
3. Open pg_hba.conf
4. Under IPV4 Local connections change ADDRESS to the correct CIDR notation
5. Navigate to windows services (Windows Key + R services.msc) 
6. Restart the service (PostgreSQL Server etc) 
7. Test the connection with a driver or Webadmin4 on another machine
8. If the above does not work open "postgresql.conf" located in the data folder
9. Add the line " listen_addresses = '*' "
10. [Credit/Direct reference](https://stackoverflow.com/questions/18580066/how-to-allow-remote-access-to-postgresql-database)
