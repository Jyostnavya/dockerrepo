*DOCKER INSTALLATION* 

Step 1: This setion guides through the Docker Desktop installation on your machine. Please follow the offical documentation link to install https://docs.docker.com/engine/install/

Step 2: After installation, restart the machine then open Docker Desktop application.

Step 3: Check the version of Docker by launching the terminal, if you are on commandprompt for Windows or terminal for Mac and for other OS launch up the shell--> docker --version

*DEVOPS USE CASES*

*DOCKER CONTAINERS*

docker run -p 5000:5000 in28min/hello-world-python:0.0.1.RELEASE

command explaination 

--> in28min/hello-world-python:0.0.1.RELEASE --> path to the docker image which is stored on the docker registry called docker hub

--> Docker Hub is public docker registery which is accessible at https://hub.docker.com/. Docker Registery contains a lot of different repositories of different versions of differnt applications.

--> When we specify the path to the image, wespecify 2 things:

in28min/hello-world-python --> Docker Repository

0.0.1.RELEASE--> Specific tag, this specific image contains everything that we need to run the specific application, it contains all the releases like right software to run your application need,libraries and also the dependencies

** Static version of the image "in28min/hello-world-python:0.0.1.RELEASE"on the repository or local machine-- image

running version of this image "in28min/hello-world-python:0.0.1.RELEASE"--container **

*NOTE* 

For one image, we have a lot of containers which are running

-p 5000:5000 --> Whenever we run a container, it is a part of internal network called Bridge by default all the containers run inside the bridge network
Containers cannot be accessed unless the port is exposed, consider the scenario here 5000:5000, the container 5000(right side) is mapped to host port(left side) and option which enable us to do this is -p, short cut for --publish


docker run -p 5000:5000 in28min/hello-world-java:0.0.1.RELEASE 
docker run -p 5000:5000 in28min/hello-world-nodejs:0.0.1.RELEASE 

*NOTE*
Once you have a docker image, it doesnot matter whether it is image of python or java or nodejs application, you can run it in the same way 
