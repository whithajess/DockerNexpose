DockerNexpose
=============

Uses the nexpose chef cookbook to create a nexpose docker container

USAGE
=============

### PULL DOWN IMAGE
docker pull whithajess/dockernexpose
###DEAMONIZE IMAGE
sudo docker run --name nexpose_container -p 49160:3780 -d whithajess/dockernexpose
###WORK OUT THE STATE
nexpose probably hasn't finished setting up all its stuff yet which is why you cant log in anyway docker attach $PID should show you wtf its up to docker ps will show running
###LOG IN
use your local browser port 49160
https://localhost:49160/
default username/password is nxadmin/nxadmin
will need to active community license here etc.
NB: can pass different configs to chef to set different defaults etc.
