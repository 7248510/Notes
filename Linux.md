# Linux Notes(The notes are designed terminal usage)
* Emptying trash on Cent
 <br> rm -rf ~/.local/share/Trash/files/*
 * Allowing remote access
    <br>For MongoDB and MySQL you have to edit their config files to allow remote access
    <br>Locating your MySQL config file = mysql --help | grep "Default options" -A 1
    <br>It's the first file from the left(/etc/my.cnf)
    <br>If bind-address isn't there you're fine. (sudo vi /etc/my.cnf)
    <br>You can also add it "bind-address=0.0.0.0" or "bind-address=127.0.0.1" for local host
    <br>I created another user with remote privileges. If you're using root you have to enable remote logins(When your installing MySQL I think you can enable remote                 <br>root...I wouldn't enable remote root! It's better to create another user)
    <br>sudo vi /etc/mongod.conf
    <br>change "bindIP: 127.0.0.1" to "bindIP: 0.0.0.0"
    <br>Then restart the service
    <br>sudo systemctl restart mongod
    <br>Find your firewall zone
    <br>firewall-cmd --get-active-zones
    <br>Open 3306 or your custom MySQL port & Mongo
    <br>sudo firewall-cmd --zone=public --add-port=3306/tcp --permanent
    <br>sudo firewall-cmd --zone=public --add-port=27017/tcp --permanent
    <br>reload sudo firewall-cmd --reload
    <br>sudo systemctl restart mysqld && sudo systemctl restart mongod

# Debian 10
If you cannot update your packages/find your sources list.
https://wiki.debian.org/SourcesList

# Note sources/Credit:
<br>https://www.tecmint.com
<br>https://stackoverflow.com/
<br>Various documentation pages
