# Django REST Framework & Docker


## A Beginner's Guide to Docker

* With Docker we now longer have to mess around with virtual environments. We can faithfully reproduce a production environment locally. And Docker can be shared among team members so everyone is working on the same setup. Wins all around.

- What’s the downside? Complexity. Docker is a complex beast under the hood. However a little knowledge can take you a long way and that’s the goal of this guide!

## Linux Containers

Docker is really just Linux containers which are a type of virtualization.

Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm. How could multiple programmers use the same single machine? The answer was virtualization and specifically virtual machines which are complete copies of a computer system from the operating system on up.

If you rent space on a cloud provider like AWS they are typically not providing you with a dedicated piece of hardware. Instead you are probably sharing a physical server with hundreds or even thousands of other clients.

What’s the downside to a virtual machine? Size and speed. A typical guest operating system can easily take up 700MB of size. So if one physical server supports three virtual machines, that’s at least 2.1GB of disk space taken up along with separate needs for CPU and memory resources.

Most computers rely on the same Linux operating system, so what if we virtualized from that level up instead? Wouldn’t that provide a lightweight, faster way to duplicate much of the same functionality?

The answer is yes. And in recent years Linux containers, also known as “containerization,” has become increasingly popular. For most applications, a virtual machine provides far more resources than are needed and a container is more than sufficient.

This, fundamentally, is what Docker is. A way to implement Linux containers!

An analogy we can use here is that of homes and apartments. Virtual Machines are like homes: stand-alone buildings with their own infrastructure including plumbing and heating, as well as a kitchen, bathrooms, bedrooms, and so on. Docker containers are like apartments: they share common infrastructure like plumbing and heating, but come in various sizes that match the exact needs of an owner.

## Containers vs Virtual Environments


If you are a Python programmer (like me) a common question at this point is, what about virtual environments? How do they differ from containers?

Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer. Virtual environments are great.

But…virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python albeit they can refer to the proper version. So when we use Python 2.7 in a project, we’re pointing to an installation of Python 2.7 on the computer itself, not actually within the virtual environment.

Also we can’t run a production database or other services within virtual environments so compared to Docker containers they are far more limited.

## Hello, World

- To confirm Docker installed correctly we can run our first command docker run hello-world. This will download an official image and then run the container. We’ll discuss both images and containers shortly.

```py 
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete
Digest: sha256:9572f7cdcee8591948c2963463447a53466950b3fc15a247fcad1917ca215a2f
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
 ```

 _A good command to inspect Docker is docker info which we can run now. It will contain a lot of output but focus on the top lines which show we now have 1 container which is stopped and 1 image._

 ```
 $ docker info
Containers: 1
 Running: 0
 Paused: 0
 Stopped: 1
Images: 1
```
_Want to inspect just the current image?_

```
$ docker image ls
REPOSITORY          TAG        IMAGE ID            CREATED             SIZE
hello-world         latest     fce289e99eb9        12 months ago       1.84kB
```

_There is the hello-world image which we just downloaded. How about inspecting containers, either running, paused, or stopped?_

```
$ docker container ls -la
CONTAINER ID IMAGE        COMMAND   CREATED  STATUS     PORTS  NAMES
c827847463a1 hello-world  "/hello"  About... Exited (0)        blissful_swartz
```

- I have shortened the actual about for CREATED and STATUS to fit but we can see the container for hello-world. The NAMES here, musing_raman, is randomly created by Docker unless we specifically set it so your name will likely be different.

Also, why do we need ls -la here instead of ls? The answer is because the container is stopped! Only running containers will appear with docker container ls.


## Images and Containers


Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.

When we ran hello-world we used an official Docker image. We did not have to create the image ourself. But typically we will create custom images and we do so using a Dockerfile. We also will use docker-compose.yml files to run the containers.

_A baking analogy we can use here is as follows:_

> A Dockerfile is the recipe for a cake

> An image is a snapshot of the recipe at a given time

> A docker-compose.yml says how to make the cake

> And the container is the actual, baked cake

- There are a large number of official images available on Docker Hub for common software like different flavors of Linux, programming languages, and so on. For example, the Hello World image is there.

## Images

Ok, let’s create our own image for something more “real.” How about the Python programming language? We can create an image and container just for Python and later add on to it.

First create a local directory on your computer for our code. I’ve chosen to make a code folder on my Desktop (I’m using an Apple computer) and then a python3.7 folder within that.

```
$ cd ~/Desktop
$ mkdir code && cd code
$ mkdir python3.7 && cd python3.7
```

Now we need to define the image with a Dockerfile. This is similar to a Pipenv or a requirements.txt file; it is a list of all the requirements needed to build our image. It is simpler to have them all in one place rather than install each manually line-by-line.

If you are on a Mac, you can create a new Dockerfile on the command line using the touch command.

`$ touch Dockerfile`

## Library Website and API


Build our first API with Django/Django REST Framework

Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework; it always must be added to a project after Django itself has been installed and configured.

In this chapter we will review the similarities and differences between traditional Django and Django REST Framework. The most important takeaway is that Django creates websites containing webpages, while Django REST Framework creates web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON.

To illustrate these concepts, we will build out a basic Library website with traditional Django and then extend it into a web API with Django REST Framework.

