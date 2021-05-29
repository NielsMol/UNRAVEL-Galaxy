# READ ME FILE FOR MANAGING GALAXY

Galaxy is managed by Ansible playbook galaxy.yml
It needs the "hosts" inventory file to know what the DNS of the instance is/ Pulsar / Monitoring
Galaxyservers (group_vars/galaxyservers.yml) is the configuration of the entire instance

## Restarting Galaxy when running ansible-playbook galaxy.yml
 If by any chance the command:         ansible-playbook galaxy.yml
 results in an error, then run the command:    Restart galaxy
 or the command:        sudo systemctl restart galaxy

## Misconfiguration explanations in ansible 
Sometimes Ansible tasks will fail. Usually due to misconfiguration, but occasionally due to other issues like your coworker restarted the server while you were doing maintenance, or network failures. Let’s say you’re running a playbook that updates the galaxy.yml, which will in turn notify the handler Restart Galaxy. If this change is made, and notification triggered, but a failure occurs before Ansible. The next time you run the playbook, Ansible will not observe any configuration files changing (because they were changed in the last run.) And so the Restart Galaxy handler will not run.
If you encounter this situation you just have to be mindful of the fact, and remember to manually restart the handler. There is no general solution to this problem unfortunately. This applies mostly to development.

## Bad gateways 502 error, nginx and certbot 
If you receive a bad-gateway error in the http://link. then this is most often due to the nginx config files. see https://training.galaxyproject.org/training-material/topics/admin/tutorials/ansible-galaxy/tutorial.html nginx for more information
It might be possible that the certbot certification goes wrong. you will need a DNS (server name) and the right specification in the group_vars/ file galaxyservers.yml
To be certain of this you can check the following directories:
- /etc/ssl/user/
- /etc/ssl/certs/
- /etc/letsencrypt/live/

### The first = /etc/ssl/user/
This is the dir that nginx is directed to when checking for the privkey,  without this privkey, the digital handshake cannot be made and you will receive the DNS error when accessing the website.

### The second = /etc/ssl/certs/
This is the dir that maintains all of the certificates of your current instance (DO NOT REMOVE THEM). This directory has the ca-certificates.pem file which contains all of the keys needed for the certification. Fullchain.pem and cert.pem of the DNS-request by certbot should be present in this dir. You may chance the fullchain and cert certifications but they should always be present when configuration via ansible takes place.

### The last one = /etc/letsencrypt/live/
This final directory is where certbot (managed by letsencrypt) uploads its requested certificates by DNS name.  When this instance was created it was given the name https://unravel-galaxy-version-21-5.fairheartgalaxy-avans.surf-hosted.nl/. So, there should be at least one directory with this name.  when it gets cloned, you will recieve more directories for the newly requested DNS. YOU WILL HAVE TO REPLACE THE FULLCHAIN.PEM CERT.PEM AND PRIVKEY.PEM FROM THIS DIR TO THE /etc/ssl/certs/ DIR, If this does not happen, then the digital handsake will not be performed and you will be unable to use certification necessary processes like shed-tools.
   
 
## Installation of SLURM                          
 Installed with Slurm is MUNGE (MUNGE Uid ‘N Gid Emporium) which authenticates users between cluster hosts. You would normally need to ensure the same Munge key is distributed across all cluster hosts (in /etc/munge/munge.key). A great task for Ansible. However, the installation of the munge package has created a random key for you, and you will not need to distribute this since you’ll run jobs only on a single host. You can now check that all of the daemons are running with the command: systemctl status munge slurmd slurmctld.
You would normally need to ensure the same Munge key is distributed across all cluster hosts (in /e$# A great task for Ansible. However, the installation of the munge package has created a random key f$# You can now check that all of the daemons are running with the command:       systemctl status mung$# Link that helps oncifuration of SLURM:        https://slurm.schedmd.com/configurator.html
Link that helps oncifuration of SLURM:        https://slurm.schedmd.com/configurator.html
Link to dynamic job configuration:            https://docs.galaxyproject.org/en/latest/admin/jobs.html#dynamic-destination-mapping-python-method


