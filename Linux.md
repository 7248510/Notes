# Linux Notes(The notes are designed terminal usage)
Emptying trash on Cent
rm -rf ~/.local/share/Trash/files/*
For MongoDB and MySQL you have to edit their config files to allow remote access
Locating your MySQL config file = mysql --help | grep "Default options" -A 1
It's the first file from the left(/etc/my.cnf)
If bind-address isn't there you're fine. (sudo vi /etc/my.cnf)
You can also add it "bind-address=0.0.0.0" or "bind-address=127.0.0.1" for local host
I created another user with remote privileges. If you're using root you have to enable remote logins(When your installing MySQL I think you can enable remote root...I wouldn't enable remote root! It's better to create another user)
sudo vi /etc/mongod.conf
change "bindIP: 127.0.0.1" to "bindIP: 0.0.0.0"
Then restart the service
sudo systemctl restart mongod
Find your firewall zone
firewall-cmd --get-active-zones
Open 3306 or your custom MySQL port & Mongo
sudo firewall-cmd --zone=public --add-port=3306/tcp --permanent
sudo firewall-cmd --zone=public --add-port=27017/tcp --permanent
reload sudo firewall-cmd --reload
sudo systemctl restart mysqld && sudo systemctl restart mongod

# Debian
If you cannot update your packages find your sources list.
https://wiki.debian.org/SourcesList

# Note sources:
https://www.tecmint.com
https://stackoverflow.com/
Various documentation pages
