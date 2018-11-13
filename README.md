# Dockerized-TensorFlow-GPU
This project contains a boilerplate setup for using TensorFlow GPU inside docker containers. It will create an image containing your python code along with the tensorflow runtime.

Makes life easier setting up a dockerized environment for running Tensorflow with GPU support from your host machine.

## What's the point? 

Setting up TensorFlow with GPU support can be really tough! Even with the premade docker image.
You still need to provision your local machine with the correct versions of the following:

* CUDA 9.0
* NVidia-Docker
* TensorFlow's Docker Base image

So I built this set of bash scripts for Debian / Ubuntu that enable you to set up and running with containerized TensorFlow with GPU support.  

## Getting started

### Setup
Simply run the setup script:

``` sudo bash setup.sh ```

and follow the on screen instructions.

Note: You'll initially be asked to accept some terms and conditions for CUDA. Pressing the "d" key multiple times is a quicker way to get to the bottom. Once you get there, assuming you've thoroughly read the terms and conditions 😜, you'll need to type "accept".

When the setup is completer the "run-code.sh" script gets automatically run. This builds a custom docker container with the sample code included and runs it in your terminal.

The code will run with GPU support inside a container.

### Executing your own custom code

Modify the main.py file inside the src/code directory to run your code simply enter the following into your terminal:

```$ sudo bash run-code.sh ```

The run script builds an image on your machine based on google's TensorFlow image. 
It will then run the main.py file.


### Run a jupyter notebook

If you'd like to run a jupyter notebook simply run enter this into your terminal: 

```$ sudo bash run-notebook.sh ```

 When running this open another terminal and type 
 
 ```$ docker ps ```. 
 
 This will give you a list of running containers. Find the notebook container and type 
 
 ```$ docker inspect {containerID} (or name works too) ```
 
 This will show you a load of stuff about the container. Find it's IP address and use this in place of the stuff in brackets in the output:
    
    example output: 
    http://(758e8f6237f3 or 127.0.0.1):8888/?token=5d0c0db567b3413f4ca33c403dd5e2c4eaef2d4c4cff1ef7

 In the example above you'd replace (758e8f6237f3 or 127.0.0.1) with the container's ip address and open that in a browser.

## Having trouble?

My goal is to make this as simple and easy to use as possible so let me know and where possible I will make this code easier to use. If you have any difficulties or are unsure about anything please raise an issue on GitHub. 
