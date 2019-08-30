# ansible-tower-stage
Staging files to install Ansible Tower binaries

updated 8/29/2019

This Dockerfile preps a container for a single instance install of Ansible Tower on a CentOS 7.6 container.
All required binaries picked up and autobuilt at docker cloud.

The Dockerfile is used by docker hub to build an image.  
Pick it up at https://hub.docker.com/r/hiramag/ansible-tower-stage

It will always pick up the latest:
   - centos/systemd image
   - ansible tower image 

Steps:
1. Create a directory example ansible-stage
2. cd ansible-stage
3. git clone https://github.com/hiramag/ansible-tower-stage.git
4. docker-compose up -d
5. docker exec -it {running image name} bash
6. /var/tank/ansible-tower-setup/setup.sh 
7. chown awx:awx /var/lib/awx/projects
8. ansible-tower-service start
9. browse https://localhost:8443
10. login as admin:password
11. get a free license and apply (https://www.ansible.com/license)
12. run the demo project (step 7 is the fix if there is a problem here)
13. ansible-tower-service stop
14 git commit {running container} {new image name}



