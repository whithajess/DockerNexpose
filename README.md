DockerNexpose
=============

Uses the nexpose chef cookbook to create a nexpose docker container

USAGE
=============

### PULL DOWN IMAGE
```bash
docker pull whithajess/dockernexpose
```

###DEAMONIZE IMAGE
```bash
sudo docker run \
  --name nexpose_container \
  -p 49160:3780 \
  -d whithajess/dockernexpose
```

###WORK OUT THE STATE
nexpose probably hasn't finished setting up all its stuff yet which is why you cant log in anyway docker attach $PID should show you wtf its up to docker ps will show running

###LOG IN
  * use your local browser port 49160: https://localhost:49160/
  * default username/password is nxadmin/nxadmin
  * will need to active community license here etc.

###LICENSING
Nexpose needs a license to work. To get one, get through their downloading process on the [Rapid7's website](http://www.rapid7.com/products/nexpose/compare-downloads.jsp).
Licensing must be done through the web interface, but then, it can be save inside a new docker image.

```bash
# once the licensing is done, save the new image
docker commit nexpose_container nexpose_licensed

# from now on, use the new image to run nexpose
docker run \
  --name nexpose_container \
  -p 49160:3780 \
  -d nexpose_licensed
```

NB: can pass different configs to chef to set different defaults etc.
