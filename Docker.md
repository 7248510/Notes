# Docker interactive
<br>docker run 
<br>-i = interactive
<br>-t = terminal
# MongoDB
<br>For hosting a local instance of MongoDB on Windows(you need to bind the external port to a local port):
<br>Pull the image with "docker pull mongo"
<br>Creates the new container: <br>"docker run -d --name nodeTest -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=changeMe -e MONGO_INITDB_ROOT_PASSWORD=horriblePassword mongo"
<br>If you need the IP address of the container enter "docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container_name_or_id"
<br>URI for the container(The ip address was found with the command above)
<br>Sample URIS:<br>mongodb://changeMe:horriblePassword@localInterface:27017/?authSource=admin(local interface)<br>mongodb://changeMe:horriblePassword@127.0.0.1:27017/?authSource=admin(localhost/127.0.0.1)
<br>docker run -d --name nodeTest -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=changeMe -e MONGO_INITDB_ROOT_PASSWORD=horriblePassword mongo (URI with local host)
<br>docker run -d --name nodeTest -p (LOCALIP/interfaceIP):27017:27017 -e MONGO_INITDB_ROOT_USERNAME=changeMe -e MONGO_INITDB_ROOT_PASSWORD=horriblePassword mongo (uri with the entered interfaceIP)
# Start,stop,delete docker container
docker rm /testing (remove/delete a container)<br>
docker rm --force testing (Stop an active container)
<br>docker start NAMEOFCONTAINER
<br>docker stop NAMEOFCONTAINER
<br><b>Credits:
  <br>https://stackoverflow.com/questions/17157721/how-to-get-a-docker-containers-ip-address-from-the-host
  <br>https://osric.com/chris/accidental-developer/2017/08/running-centos-in-a-docker-container/
  <br>https://stackoverflow.com/questions/34559557/how-to-enable-authentication-on-mongodb-through-docker
  <br>https://stackoverflow.com/questions/17157721/how-to-get-a-docker-containers-ip-address-from-the-host
  <br>https://www.code4it.dev/blog/run-mongodb-on-docker
  <br>https://docs.docker.com/
  <br>https://stackoverflow.com/
