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

Now again suppose thatn you want to deploye a flask web app on server, for that you will need apachhe,ubuntu,etc packages, so you install them on your srever and make a docker image of it, now you can move that docker image any where and extract a container from that image.

- a container is made from an image, image is the blue print of how to make a container:
- that blueprint can be like : first install ubuntu then apt get apache then apt get update,
- means if you want to run some files in sequence then you can put them in docker and make a image for it.
- install java, set path, pip recognise issues , all  these problems you will have to deal only once.
- just make an image for it, and put that image in container when ever needed
- suppose I made a conatiner in my machine using a docker image, now if ubuntu was installed in that container, we can go inside that container, if ubuntu is install in that conatiner we can go and run any ssh. command in ubuntu and commit it, and save it as a deifferent image2, can also send this image2 to other computers and aslo do some alterations there and save as image3.

![docker1](https://user-images.githubusercontent.com/33677647/215383298-9cc0bff8-04e8-4541-883d-025b521330e3.png)
![docker2](https://user-images.githubusercontent.com/33677647/215383305-931ee6f0-0691-4a57-ad42-40ee63c504a1.png)
![docker3](https://user-images.githubusercontent.com/33677647/215383309-a085be72-fbae-4ee4-9132-df0cc90d5e9d.png)
![docker4](https://user-images.githubusercontent.com/33677647/215383321-7fe6ef9f-91ed-44d5-bc7e-d755e349d106.png)

### Docker Hub :
it is a hub of that has repositories stored online, that hosts dockers images
- you can pull docker images from their and install on your pC and make a container
