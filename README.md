Steps.

1 - On local machine -jenkins master- terminal type "ssh-keygen" to generate the key pair to connect to the another machine.

2 - On slave -jenkins node/builder- machine, we type on console "ufw status" to verify if firewill is connected, if do, type "ufw disabled" to turn it off.

3 - On the slave console, we need to install the java version we want. On ArchLinux we can do it by the following command: "sudo pacman -Sy jre-openjdk21".

4 - Now, on slave console we type "ipp addr" or "ifconfig" to know the ip of our slave machine.

5 - On master console, we type "ssh-copy-id slave-machine-username@slave-machine-ip" to connect to it via SSH. 

6 - Once done, we can verify this by this simple command: "ssh slave-machine-username@slave-machine-ip". We should now be ables to have a succesful connection to the slave machine.

7 - Now, on jenkins master dashboard page, we go to Manage Jenkins, Nodes, New node
