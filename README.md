# docker-cmd


- docker-compose up -d  -------> launch airflow
- docker-compose down -v ------> shutdown airflow containers +remove volumes of docker .yaml file(helps to Stop and remove containers, networks, images, and volumes.)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Docker 

- docker is a company, that provides containers (containerization as a concept).
- like gamil is a company , that provides emails service.

### So what is containarization ?<br/>

Suppose you have deployed an app (like a website) on server, on your manager says that move this app from this IP address to this IP address, now you will have to repeat the process of downloading all packages again<br/>

Also it might not work on other machine due to some changes in version.<br/>

If it is working on your machine but not on your co-workers machine because of difference of versions<br/>

All these problems are solved by containers of docker<br/>

If you install a VM on your PC, it installs an OS on your machine, so you will have to configure every thing like, how much CPU how much RAM andf installing process of VM, all this slows your computer<br/>

Whereas docker only takes the memory that is needed to deploye your  webapp , It does not install any operating system on your machine like a VM.<br/>

Docker's containers only takes the resources that are required for your webapp
