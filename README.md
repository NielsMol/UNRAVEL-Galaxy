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

