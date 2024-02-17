First, we run this command to create a container of Jenkins on docker: "docker run --name jenkins -d -p 9800:9800 -p 50000:50000 -e JENKINS_OPTS='--httpPort=9800' -v jenkins-data:/var/jenkins_home jenkins/jenkins:lts-jdk21"

And then, on VirtualBox, we create a virtual machine based on ArchLinux, and configure it on network "bridged" instead of "NAT" to be ables to connect to it.

Once we have a jenkins docker container running and a virtual machine succesfully up, we can continue.

Steps.

1 - On local machine -jenkins master- terminal type "ssh-keygen" to generate the key pair to connect to the another machine.

2 - On slave -jenkins node/builder- machine, we type on console "ufw status" to verify if firewill is connected, if do, type "ufw disabled" to turn it off.

3 - On the slave console, we need to install the java version we want. On ArchLinux we can do it by the following command: "sudo pacman -Sy jre-openjdk21".

4 - Now, on slave console we type "ipp addr" or "ifconfig" to know the ip of our slave machine.

5 - On master console, we type "ssh-copy-id slave-machine-username@slave-machine-ip" to connect to it via SSH. 

6 - Once done, we can verify this by this simple command: "ssh slave-machine-username@slave-machine-ip". We should now be ables to have a succesful connection to the slave machine.

7 - Now, on jenkins master dashboard page, we go to Manage Jenkins, Nodes, and we can create a new Node for Jenkins! 
