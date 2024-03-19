```diff
+ Docker enables you to separate your software from your infrastructure for fast delivery
```
![image](https://github.com/sundas586/docker-cmd/assets/33677647/d8f5aa01-b266-4e2a-9acc-4a765c64a192)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/c8d4f87f-70db-442d-be4b-73b60b00ef8d)

### Tag (image name)

- when we don't give a name to an image, docker by defaults give it a tag name '**latest**'

  ![image](https://github.com/sundas586/docker-cmd/assets/33677647/536ef842-1fcc-4120-b1d9-b23090f9fbf6)

### List of docker images

![image](https://github.com/sundas586/docker-cmd/assets/33677647/02573cf6-5146-4345-99a6-a9ea97e3a56b)

### To run an image, we do not need to pull it first, we run the image and if it is not available in `docker ls` docker will pull the image automatically and then run this image.

![image](https://github.com/sundas586/docker-cmd/assets/33677647/785fc21f-ba97-4792-ad68-0073a0ca8903)

- In the first command, we check that our docker has no image
- In the second command we directly **RUN** an image and also give it a name **C1** so docker first **PULL**s the and then runs it as a container.
- In the third command we see that yes we do have a running container with the name C1
![image](https://github.com/sundas586/docker-cmd/assets/33677647/ab1a10f0-96cb-46f1-89bf-fa5332431ce3)


### to remove an image 

- rmi = remove image
![image](https://github.com/sundas586/docker-cmd/assets/33677647/ef2967ec-9f72-4fc0-8587-3c0fb35973b4)

### OK! So you created a running container inside docker BUT!! How to bind it to the outside world (by : PORT BINGING)

- Here we are binding the port of our local machine/PC/Server (8081) to the port of our docker container (80)
- After binding the ports like this, **We can access our container from anywhere in the world** or from local browser, just by providing the IP & the port

![image](https://github.com/sundas586/docker-cmd/assets/33677647/bc8ceab9-369b-4fcf-a9e6-90a4de6c13cb)

![image](https://github.com/sundas586/docker-cmd/assets/33677647/75228757-9e74-49f1-a3a2-e39dca7e3c8e)

### Let's check our used ports & Networks (also what is the command: netstat tulnp)

- As we had to bind our port 8081 of the local server/ machine to port 80 of docker

  ![image](https://github.com/sundas586/docker-cmd/assets/33677647/aa7d171d-7ab2-4e29-867a-548beb41ca78)
  ![image](https://github.com/sundas586/docker-cmd/assets/33677647/936b60e3-5c2d-425c-bb18-b8b806e0e21d)

  ```diff
  + Since we can always change the port number of the local machine
  - But the port number of a container can not be changed
  @@ To change the port number of the local machine we can check which ports are available using `netstat tulnp` command @@
  ```


### IP address of container

- So as we have bind the port 8081 of our machine to port 80 of Docker.
- We just need to provide IP address and the port 8081 will route the traffic to port 80
![image](https://github.com/sundas586/docker-cmd/assets/33677647/442c4777-32ff-4bc0-afae-04bdd090b657)

- **ip a**
  
![image](https://github.com/sundas586/docker-cmd/assets/33677647/6a34e85c-419f-46d5-8f89-5b006ec6f78c)
- You can see the IP address of each interface listed under the **inet** field
![image](https://github.com/sundas586/docker-cmd/assets/33677647/b9ec67e9-7c33-40ba-94ef-fb07cee8d360)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/6340d585-d0f8-43e4-ad7f-929780e3bc43)
- your machine IP + port
  ![image](https://github.com/sundas586/docker-cmd/assets/33677647/9d546969-780a-4113-a1e5-fc2bc87db985)

### How to check the LOGS  of a container

- In the first command, we are running a container and also giving it a name
- In the second command, we are checking its logs (we can either give the container ID or the container name to check logs)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/4ceb6ea7-aa5f-4e78-ab39-b86f2b282a2b)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/c650fdbf-4311-4490-a6d6-636b2ed0b18e)

### If you want full info about any Image/ Container/ Volume then use : "DOCKER INSPECT"

- The docker inspect command is used to get the full info of any docker object (e.g Image, container, volume)
- It has a detailed JSON-formatted output
- Container ID
- When this container was created
- What are the arguments
- What is the state
- Which Image was used to create this container
- Where is the log file of this container
- Mount
- Restart count
- Entry Point

- **Docker inspect containerID/ containerName**
- **Docker inspect ImageID**  
![image](https://github.com/sundas586/docker-cmd/assets/33677647/41a0d2c8-d656-4fd5-bd24-0d6ae10c2fbd)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/a0f5f6c3-b4be-4236-93e8-867cc9c1a917)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/8196fd7d-7226-4a0e-b2a8-248b01d2c18a)


# Docker Network:

- A Docker network is a virtual network that allows Docker containers to communicate with each other and with external networks. 
- It provides isolation and security for containerized applications by creating separate communication channels.

## Types of Docker Networks:

- Docker supports various types of networks to accommodate different use cases:

1_ Bridge Network (Default network/ Docker0)<br/>
2_ Host Network <br/>
3_ None Network <br/>

![image](https://github.com/sundas586/docker-cmd/assets/33677647/a310b382-ac22-4066-9cfb-6e6dd5a3ad79)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/a17b3197-7f26-491b-9cc5-724afbe50444)

- Any container we create is by default on the bridge network (Docker-0)

  ![image](https://github.com/sundas586/docker-cmd/assets/33677647/920badd5-15a0-4a2f-a95c-cd9df7a4c34d)


- To check how many networks we have on our machine
- **Docker network ls**
  ![image](https://github.com/sundas586/docker-cmd/assets/33677647/9410821c-76f0-4c97-8d9e-897e16723266)
 
```diff
+ so what i inderstand is k any container we create uses Bridge network (Docker-0) by default and therefore it uses our machines local IP and the assigned port number to that specific contaoner
```
- local IP
![image](https://github.com/sundas586/docker-cmd/assets/33677647/0747b709-da63-4d85-8b88-bf5380f9bc41)
- 8081:80 is the port binding for c3
![image](https://github.com/sundas586/docker-cmd/assets/33677647/8bab9f39-77cf-4cf7-9262-a6851d9b6597)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/8555ba2c-5f86-4d7f-ace5-6f801fdae4a1)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/3a56e903-4898-46e3-a44e-e7d48bdb9a35)
![image](https://github.com/sundas586/docker-cmd/assets/33677647/7b96c96c-58d5-4303-8bf1-34008992b5a2)



--DRIVER = bridge/host/none


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
- **Soluntion** : just put a "-d" in the same command when doing the up of container to ye ub terminal band ya stop krnay k bad bhi background m container run krta rahay ga
- (-d : run the container in background and not only on front console, If you don't put -d so your container will run only on front console and once you close your tab, container will be down again):

![1](https://user-images.githubusercontent.com/33677647/224898020-3d703c8c-bb02-4efc-a263-db5b58733a78.png)

- In Docker, the **"-d" flag stands for "detached" mode**.
- When you run a Docker container with the "-d" flag, it means that the container will run in the background (detached mode), allowing you to continue using your terminal for other tasks without being tied to the container's output. It's commonly used when you don't need to interact with the container directly but still want it to run in the background.

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

