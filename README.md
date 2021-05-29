# The federal UNRAVEL-Galaxy data analysis platform
This page contains the information of how to construct and customize the UNRAVEL-Galaxy instance. It imported all playbooks Galaxy-ansible playbooks that were used, a manual on how the VM-templates were generated and the Cardiomyopathie lines count-files for differential-expression analysis.

## The Fairheart-Galaxy
This instance was made using the project of Fairheart-in-the-cloud-with-Galaxy as its basis. This project laid the fundamentals of the UNRAVEL-Galaxy as it is customized from the FairHeartGalaxy instance. The markdown of the project is available through this GitHub link: https://github.com/NielsMol/Fairheart-in-the-cloud-with-Galaxy.

## Why construct a private Galaxy? 
There are already larger and far more improved Galaxy instances available like https://usegalaxy.eu/, and  https://usegalaxy.org/. These Galaxy instances are free to use, so why create your own private one? Galaxy is open-source and fully public. My accepting the terms and conditions of data, they will protect your personal data, but cannot promise to do the same for the data you analyze. The General data protection regulations that were implemented in may of 2018 do require you to do so for controlled personal data. Constructing, managing and securing your groups private Galaxy is a solution to this challenge. 

## Features of this page:
- Complete Markdowns of both the project in SURF and in DRE
- Examples of the most important files such as playbooks and config-files
- Flowcharts used to explain the improvements to be made for managing and scaling a federal Galaxy
- List of installed tools used for the Analysis of RNA-seq CM-data
- Details of VM-designs and manuals used to build a template in SURF and DRE
- A list of external access IPs used for DRE
- Count-files and extra information concerning the CM-datasets
- A universal workflow for RNA-seq analysis of paired and single-end data in Galaxy

## What is Galaxy?
Galaxy is a simple click-through data analysis platform that does not require a bioinformatics skillset to perform data analysis
As a user, you will only see the interface of Galaxy, no personal scripting or coding is necessary

![alt text](https://github.com/NielsMol/UNRAVEL-Galaxy/blob/main/Galaxy_click-through_overview_from_user_perspective.png)


## Schematic overview of the current UNRAVEL-Galaxy construction
![alt text](https://github.com/NielsMol/UNRAVEL-Galaxy/blob/main/Overview_of_project_UNRAVEL-Galaxy_construction.png)

Ansible was used for building and maintaining the first images on SURF. Docker was used to pull the image from SURF to DRE.

## Overview of possible next phases of the project
![alt text](https://github.com/NielsMol/UNRAVEL-Galaxy/blob/main/Long-term_Theoretical_overview_of_the_UNRAVEL-Galaxy.png)


## Issues and Bugs encountered during this project
- Remote access error to access SURF VMs
- External access failed data pulls from the net when using DRE
- Outdated certifications by Certbot
- Disruption of Slurm as job cluster system
- Daemon docker automation failed

## License
This project was made possible thanks to Avans University of Applied Sciences and the University Medical Centre of Utrecht in the Netherlands. SURF provided the necessary computational resources to start and continue this project. The anDREa consortium provided access to DRE for a secure data analysis environment and storage. This project used trainings provided by the Galaxyproject to construct the instances. These trainings are available for free at https://training.galaxyproject.org/training-material/topics/admin/tutorials/ansible-galaxy/tutorial.html.

