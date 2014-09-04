This workspace is intended to create a Docker Environment with Jenkins setup. This can be very easily configured and modified as per convenience.

I am going to use this for setup of Jenkins Workshop environment for the attendees. Each attendees can spinup a docker instance using following commands.

Pre-requisite :
  1. Mac/Linux
  2. Docker


Commands:

boot2docker start

Note: Look for which tcp IP address docker asks to export.
export DOCKER_HOST=tcp://192.168.59.103:2375

docker build -t jenkins .
docker run -d -P --name workshop1 -t jenkins
docker port workshop1 8080

docker ps

Note: Now look for IpAddress and Port ID.
http://192.168.59.103:49153/


Note: For giving access to multiple users in workshops incase you decide to spin-up instance at your machine, may need to expose docker ports as your local port. Please go through Port forwarding in VirtualBox Network Settings

Note:  If exposed your machine as jenkins.local on local LAN, then you can access following environment by hitting from Closed network.

http://jenkins.local:49153/
http://jenkins.local:49154/
http://jenkins.local:49155/


Note: Copy command incase needed
docker cp account1:/var/lib/jenkins/.jenkins/jobs/ .
