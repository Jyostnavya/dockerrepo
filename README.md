Docker Installation
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

1. in28min/hello-world-python --> Docker Repository

2. 0.0.1.RELEASE--> Specific tag, this specific image contains everything that we need to run the specific application, it contains all the releases like right software to run your application need,libraries and also the dependencies

** Static version of the image "in28min/hello-world-python:0.0.1.RELEASE"on the repository or local machine-- image

running version of this image "in28min/hello-world-python:0.0.1.RELEASE"--container **

*NOTE* 

For one image, we have a lot of containers which are running

-p 5000:5000 --> Whenever we run a container, it is a part of internal network called Bridge by default all the containers run inside the bridge network
Containers cannot be accessed unless the port is exposed, consider the scenario here 5000:5000, the container 5000(right side) is mapped to host port(left side) and option which enable us to do this is -p, short cut for --publish

* MULTIPLE INSTANCES OF THE SAME APPLICATION RUNNING*

  docker run -p 5000:5000 in28min/hello-world-python:0.0.1.RELEASE

  docker run -p 5001:5000 in28min/hello-world-python:0.0.1.RELEASE  // Running the application on different ports
  


docker run -p 5000:5000 in28min/hello-world-java:0.0.1.RELEASE 
docker run -p 5000:5000 in28min/hello-world-nodejs:0.0.1.RELEASE 

*NOTE*
Once you have a docker image, it doesnot matter whether it is image of python or java or nodejs application, you can run it in the same way

DETACHED MODE AND LOGS

Launch up the container in detached mode ---> docker run -d -p 5000:5000 in28min/hello-world-nodejs:0.0.1.RELEASE

command to check the logs --> docker logs container_id

command to follow the logs with specific application  --> docker logs -f container_id

DOCKER IMAGES AND CONTAINERS

docker images //displays the list of images

docker container ls //displays the list of running containers

docker container ls -a //displays the list of all containers including the exited containers

docker container stop container_id // stops the container

** UNDERSTANDING DOCKER POPULARITY -- TOP 3 REASONS **

1. Standardized Application Packaging - Same packaging for all types of application either java or python or JavaScript, you would build the docker image

2. Multi Platform Support - Once the docker engine is installed, we can run the created docker images anywhere either on Local machines, data center, Cloud - AWS, Azure, GCP

3. Light-weight Support - Containers are light- weight as compared to VM's, Isolate from one another

Before the era of Docker, we can virtualize something with the help of Virtualization

(Add deployments using Virtual Machines diagram,see notes )

With Virtual Machines, there are 2 Operating systems i.e., Host OS and Guest OS because of which VM's are heavy weight. When we virtualize , we may not be able to use the entire power of hardware because of virtualization, now docker comes into picture.

Add Deployment using Docker diagram.

STEP 9: DOCKER IMAGES - COMMANDS

--> docker images // displays all the images

--> docker pull mysql // only pulls the images but will not run the container for it 

--> docker search mysql  //To find out the different images present in the docker registry -- look for the official images

--> Docker images are built in number of layers - layer with OS, layer with software, layer with Specification binary , to see the layers inside the image

    docker image history in28min/hello-world-java:0.0.1.RELEASE --> //in28min/hello-world-java is the repository name and 0.0.1.RELEASE is the tag name

                OR

    docker image history image_id

--> Details behind each of the images can be checked using docker inspect commmand

    docker image inspect image_id

