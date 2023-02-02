# docker-cmd


- docker-compose up -d  -------> launch airflow
- docker-compose down -v ------> shutdown airflow containers +remove volumes of docker .yaml file(helps to Stop and remove containers, networks, images, and volumes.)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Docker 

- docker is a company, that provides many tools, one of those is docker engine, that creates containers (containerization as a concept/ containers are like VMs).
- like gamil is a company , that provides emails service.

### So what is containarization ?<br/>

- Suppose you have deployed an app (like a website) on server, on your manager says that move this app from this IP address to this IP address, now you will have to repeat the process of downloading all packages again<br/>

Also it might not work on other machine due to some changes in version.<br/>

If it is working on your machine but not on your co-workers machine because of difference of versions<br/>

- suppose you developed a app and when it goes to testing team, your product doesnt work because of difference of just one sigle software having different version

- and also suppose you download pubg game in your cell, after 100% download, you get a list of errors, now as pubg is used world wide, ofcourse the problem is not in software but in your PC/mobile, so sometimes things also cause issue due to not usutable hardware.

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
![docker3](https://user-images.githubusercontent.com/33677647/215383309-a085be72-fbae-4ee4-9132-df0cc90d5e9d.png)
![docker4](https://user-images.githubusercontent.com/33677647/215383321-7fe6ef9f-91ed-44d5-bc7e-d755e349d106.png)
![lmlm](https://user-images.githubusercontent.com/33677647/215383683-0a0c30a6-1774-4a3f-991c-76b983d362ae.png)

### Docker Hub :
it is a hub of that has repositories stored online, that hosts dockers images
- you can pull docker images from their and install on your pC and make a container

## VMs vs Docker

Before VMs one server was able to host only one OS but now in case of VMs we download kernel on our servers which helps in dividing our resources of machine for differnt OS,

- VM virtualizes hardware.
- Docker virtualizes operating system.

![1](https://user-images.githubusercontent.com/33677647/216335490-c28ffe88-02ee-4620-826f-9721ce4737ba.jpg)
![2](https://user-images.githubusercontent.com/33677647/216335502-f40b1184-4c0a-412e-8848-efdad3495ef5.jpg)
![3](https://user-images.githubusercontent.com/33677647/216335506-d5819ccf-11ac-40c9-8708-dd02f20c7f79.jpg)

continue lecture from :
https://www.youtube.com/watch?v=vWjP3fsfgrw&t=908s

then follow :
https://www.youtube.com/watch?v=h17po-0DfWE


