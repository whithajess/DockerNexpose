DockerNexpose
=============

Uses the nexpose chef cookbook to create a nexpose docker container

USAGE
=============

###BUILD IMAGE
sudo docker build -t nexpose .
###DEAMONIZE IMAGE
sudo docker run -d --name nexpose-server nexpose
###FIND OUT IP
sudo docker inspect --format '{{ .NetworkSettings.IPAddress }}' nexpose-server
###WORK OUT THE STATE
nexpose probably hasn't finished setting up all its stuff yet which is why you cant log in anyway docker attach $PID should show you wtf its up to docker ps will show running
###LOG IN
use your local browser port 33780
https://172.17.0.3:3780/ (replace with your ip)
default username/password is nxadmin/nxadmin
will need to active community license here etc.
NB: can pass different configs to chef to set different defaults etc.
