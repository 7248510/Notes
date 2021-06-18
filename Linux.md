# Linux Notes(The notes are designed terminal usage)
* Emptying trash on Cent
 <br> rm -rf ~/.local/share/Trash/files/*
 * Allowing remote access
    <br>For MongoDB and MySQL you have to edit their config files to allow remote access
    <br>Locating your MySQL config file = mysql --help | grep "Default options" -A 1
    <br>It's the first file from the left(/etc/my.cnf)
    <br>If bind-address isn't there you're fine. (sudo vi /etc/my.cnf)
    <br>You can also add it "bind-address=0.0.0.0" or "bind-address=127.0.0.1" for local host
    <br>I created another user with remote privileges. If you're using root you have to enable remote logins(When your installing MySQL I think you can enable remote                  
  root...I wouldn't enable remote root. It's better to create another user)
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
 * View network information(active ports) & enable http on CentOS
  <br>ss -l(netstat is not on CentOS 7 by default)
  <br>If you cannot access pihole's interface on CentOS firewalld is blocking the connection 
  1. Make sure lighttpd's service is running with (sudo systemctl status lighttpd) if the service is running.<br>Test that the machine is hosting an interface with    curl -I 127.0.0.1 or curl (static ip pihole's configured on)<br>
  If curl shows that the interface(default webpage) is active, the firewall settings need to be changed.
  2. List your active zone (firewall-cmd --get-active-zones)
  3. Add the service that you'd like unblock to the zone of your choice (sudo firewall-cmd --zone=public --add-service=http)
# Debian 10
If you cannot update your packages/find your sources list.<br>
https://wiki.debian.org/SourcesList

# Security Onion
<br>Bridged & Host network settings
<br>sudo dhclient -v -r
<br>ip a | grep enp
<br>sudo ifconfig INTERFACE ip/subnet(10.x.x.x/x) netmask [255.x.x.x] broadcast 10.x.x.255 up
<br>sudo ifconfig enp0s8 192.168.56.2/24 netmask 255.0.0.0 broadcast 192.168.56.255 up [Example]
<br>Security onion requires a <b>router(PfSense)</b>, I attempted to configure Security Onion without a router and it didn't work!
<br>It's insane how much is logged, with an IDS. 
<br>Seeing a port scan while your IDS is logging is amazing(granted your the one conducting the scan). Sidenote; its not stealthy at all...
# Fedora
<br>nmcli is on Fedora by default(Server)
<br>sudo dnf install NetworkManager-tui | to install nmtui(the GUI of nmcli)

# Kali
<br>To disable auto suggestion uninstall the plugin.<br>Via the instructions in the repository.https://github.com/zsh-users/zsh-autosuggestions#enable-asynchronous-mode<br>
command = sudo nano ~/.zshrc
Edit this in "~/.zshrc" or COMMENT the code
<code>
if [ -f /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh ]; then
    . /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh
    # change suggestion color
    ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=#999'
fi
<code>
<br>then type in "sudo rm -rf ~/.zsh/zsh-autosuggestions"
 <br> Auto suggestion will be disabled!


<br>To install Visual Studio Code.<br>Download the debian package, navigate to your downloads folder and in a terminal execute<br>sudo apt install ./code_versionnumber (while in the packages download location. if not specifiy the folder location)

# Note sources/Credit:
<br>https://www.tecmint.com
<br>https://stackoverflow.com/
<br>https://www.computerhope.com/
<br>https://www.digitalocean.com/
<br>Various documentation pages

