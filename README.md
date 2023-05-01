[Docker cheat sheet link](https://dockerlabs.collabnix.com/docker/cheatsheet/)

## Purpose of using docker :

Docker allows developers to package their applications and dependencies into lightweight and portable containers, providing consistency, isolation, and scalability benefits. It simplifies application development, deployment, and management across different platforms and environments.

![dockr](https://user-images.githubusercontent.com/33677647/224891125-7b8f18e7-37a1-4317-8ccc-78d4308407bc.png)

suppose your app requires specific softwares with specific versions, then you can store all these pakages info in docker file, then every time your want to use this App the dockerfile will be read to spin the container, and here this container will ack as a independant computer deploying your App in it each time when you spin the container

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

 - a Docker image is a static snapshot/ **blue print of an application and its dependencies**, while a Docker container is a running instance of that image. Images are used to create containers, and containers are used to run applications in a portable and isolated manner.
 
 - A Docker container is a **executable unit**. Docker container is a running instance of that image. 
 - One image can create many containers.
 - Image ia a blue print of app. and containers runs the app in isolated & portable environment.

# dockerfile.file Vs docker-compose.yaml

- a dockerfile.file is used to create a Docker image (base image/blue print of the application)
- a docker-compose.yaml file is used to manage a set of Docker containers that make up an application.
-  Both files are important and work together to provide a complete solution for deploying and managing Docker applications.

# why do we include requiretments.txt in dockerfile?

We include requirements.txt file in Dockerfile to manage the dependencies of the Python application. requirements.txt file lists all the Python packages and their versions required by your application, and Docker can use this file to install the packages inside the container.

When we build a Docker image, Docker uses this file to create a new image. The RUN command in the Dockerfile is used to execute commands inside the container during the build process. So, we can use the RUN command to install the Python packages required by the application, by running the pip install command inside the container.

By including the requirements.txt file in the Dockerfile, we can ensure that the exact same versions of the required Python packages are installed inside the container, regardless of the host system or the environment where the container is running. This ensures that the application runs consistently across different environments and is not affected by any differences in package versions or dependencies.

# docker build vs docker-compose up vs docker run :

- docker build is used to build a Docker base image defined in dockerfile. 
- docker run first creates a new container from an image (the name of that image you give the in command) and then it also runs-up that container (This Up's only one container).
- ----> "docker run -p 80:80 nginx" (In this example, the -p option is used to map port 80 of the container to port 80 of the host machine, and nginx is the name of the image to use. When you run this command, Docker will create a new container from the nginx image, and start the container with port 80 of the container mapped to port 80 of the host machine.)
- docker-compose up is used to start a group of related Docker containers defined in a docker-compose.yml file. (Up's many containers simultaneously).


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


## PORT MAPPING (of Containers Port) : 

Each container (which has to be displayed on the web browser, like airflow-web-server or jupyter) has its own port at which all the trafic will be directed, you have to configure this port of your container if its not getiing configured by default.
In the imgae below, the port number on the left side is of our machine/server/pc(which must have its own IP address as well) and the port number on the right side is of our Airflow webserver (Airflow container).

![port](https://user-images.githubusercontent.com/33677647/224895620-7d17a5ec-1796-4388-8427-a58d5096fea1.png)

## Setting a container in docker :

- Running a command "**Docker run -p 8080:80 ngix**", to run a ngix container in docker with server port 8080, and container port 80.

## ISSUE :

- ub agr m apna terminal jahan m nay docker ko up kiya tha or port mapping wagaira kr rahi thi to agr m osay crtl+C kr k band krdun to docker container band hojayega : HAN.

- To ub m esa kiya krun k agr m apna terminal band kr dun to bhi mera docker image chalta rahay  :
- **Soluntion** : just put a "-d" in the same command when doing the up of container to ye ub terminal band ya stop krnay k bad bhi background m container run krta rahay ga :

![1](https://user-images.githubusercontent.com/33677647/224898020-3d703c8c-bb02-4efc-a263-db5b58733a78.png)

- or ye jo is command k nechay hi itna lamba ha number nazar a raha ha ye terminal hamay bta raha h k bhai ye is id wala container back ground m run horaha ha.

![1](https://user-images.githubusercontent.com/33677647/224898568-f48d02b7-fe86-4ccc-a9ef-a38848137ad0.png)

- To check which containers are up and running in your machine/server : "docker ps"

![1](https://user-images.githubusercontent.com/33677647/224901288-e24e391a-62f9-405c-b934-bb84b70b0a1d.png)

- To force stop a container that you ran  with -d in command so its running if you even close the terminal or do crtl+ C : "docker stop (some digits of the id of that container)"

![1](https://user-images.githubusercontent.com/33677647/224903770-64f237d2-6e7e-4e8a-917b-d07eea9846b5.png)
![1](https://user-images.githubusercontent.com/33677647/224908722-5475df91-d649-413c-bada-6097b6fcd06e.png)

To stop a continuesly running conatiner, just write "docker stop some begining digits of that id", make sure digits dont match with the id of any other container warna dono band hojayengay

- To check check containers I ahd ran before : "docker ps -a"
- To allow/open a port number for my PC/Server : "ufw allow 5000", so now 5000 port can be used as a port of this server.
- To delete all unnecessary containers : "Docker system prune", suppose you made so many containers for practice and now you want to delete them as they are also taking space, then docker system prune command 

![1](https://user-images.githubusercontent.com/33677647/224909451-6ad40f7f-1a91-431a-a2cc-885843235507.png)

- To go inside a container and to run a bash command inside that container (like creating a file)  : "docker exec -it 1f12 bash"
To ye kr k m apni docker container jis ki ID : 1f12..... ha os k andar a gai hu  or m un is container k andr koi bhi bash command run kr skti hun e.g file bnana , delete krna, etc.

![1](https://user-images.githubusercontent.com/33677647/224913631-dcb7352d-69b7-40ad-ab1f-fc98296b37c5.png)

- 45 meri Docker machine ka IP number tha, lakin  ye oper wali command chala k m container k andr a gai hun to ub machine number k bjaye container number 1f12 show horha ha, ub mjhy is container k andr ak new text file bnani ha jis k liyai VIM ya Nano text editor ki zrurt ha. to ub vim downloiad krny k liyai pehlau hum nay container ko update kiya phir vim download kiya .

![1](https://user-images.githubusercontent.com/33677647/224927675-1db186bc-3c66-4bd3-a662-47b740cb1dd3.png)

- to get out of container : "exit"

![1](https://user-images.githubusercontent.com/33677647/224928504-6eaf1a95-02c2-4ed1-9038-ed3a3f31ee3f.png)

- to save a file from local machine/VM/ server to a docker container : "docker source-file destination" : "docker abc.txt 1f12:xyz.txt" 

- to see all the images of docker : "docker images"

![1](https://user-images.githubusercontent.com/33677647/224958037-bf36c089-c09c-4f80-b0f3-4869829d1159.png)

- to make the container out of an image : "docker run image-id"
- and to run container when terminal is closed : "docker run -d image-id"

![1](https://user-images.githubusercontent.com/33677647/224959654-4aaee196-1ef3-470e-b079-5fe37e4eee27.png)

### docker commit

If you made some changes in a container and you want to save the image of this modified container. then use the "docker commit container-id" command.

![2](https://user-images.githubusercontent.com/33677647/224961929-18e40ded-e017-4fcf-9fbb-2c4298a04f79.png)

Now as I had downloaded a software called Vim in this container and also created some text files, now I want to make a image of this modified container, that I can do with docker commit :

![1](https://user-images.githubusercontent.com/33677647/224964444-311995fe-14e3-43c0-9a9c-31c7db8e3f4b.png)

- Here in below image we are downloading an image named "centOS" from dockers hub image repository, 
- using command "pull image centOS"
- the making a container out of that image 
- then getting into the bash terminal of that container
- then exit the container
![1](https://user-images.githubusercontent.com/33677647/224971187-66d3725e-0f59-4382-ac34-226c4c04c222.png)

- docker-compose up -d  -------> launch airflow
- docker-compose down -v ------> shutdown airflow containers +remove volumes of docker .yaml file(helps to Stop and remove containers, networks, images, and volumes.)



## Command List:
docker run nginx
docker run -p 8080:80 nginx 
docker ps 
docker ps -a 
ufw allow 8080 
docker stop <first few letters of Container ID>
docker run -d nginx // starts nginx docker container in background
docker rm CID
docker rm -f CID/name // delete a running container forcefully
docker start CID/name
 
touch this.png
docker cp this.png <first few letters of Container ID>:th.txt
docker exec -it <first few letters of Container ID> bash

docker cp <first few letters of Container ID>:mine.txt this.uu // copy from container to source
docker exec -it <Container_ID> bash // executes a command inside an existing container
docker commit container 

docker images 
docker image ls 
docker system prune

