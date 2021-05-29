# Issues 
As most issues displayed in these sections are solved, they did take up significant time during this project. Feel free to view what they were and what caused them. Some issues are not fully fixed yet and are still (rarely) encountered as bugs.

## The Daemon docker issue in DRE
The daemon is necessary for docker containers to be pulled and installed correctly. If docker cannot trace the container, it cannot be installed either. To solve this, the daemon had to be manually configured and started with the dockerd command. A JSON-file was made in ubuntu: /etc/docker/daemon.json. The file is added to the GitHub page.

## External access through IP
This list is made available in docker and is accessible using the link: 
These IPs have to manually accessed. Finding them can be done through online websearchers or by using the wget function in linux with the EXACT URL!

### Links to the IP-list
Numbers 1-15: https://github.com/NielsMol/UNRAVEL-Galaxy/blob/main/Issues/IP-list-DRE_1-15.png
 
Numbers 15-28:https://github.com/NielsMol/UNRAVEL-Galaxy/blob/main/Issues/IP-list-DRE_15-28.png

## The Outdated Certifications
Cerbot certifications do not always get automatically renewed and sometimes need some manual processing to place the ssl-certificates in the right directories. An explanation about this is added in the README of the Galaxy directory in this GitHub page.

## Remote Access
SURF and DRE both require you to access their cloud-VMs through either Secure Shell protocol (SSH) or remote desktops. SURF uses SSH, which requires you to correctly administer and store your public-keys. This process is more deeply described in the HPC cloud documentation
