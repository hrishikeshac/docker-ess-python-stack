# Docker-ESS-Python-Stack
==============================

### The goal of this project is to create a gentoo-based docker image pre-installed with open-source tools and python packages widely used in earth system data analysis.
--------
## Why bother?
Novice climate researchers, or veterans changing over to an open source environment, often finds themselves lost in getting around installing several open source tools such netcdf operators (NCOs), climate data operators (CDOs), and several of python packages useful for doing climate research.

Our goal here is to provide a docker image pre-built with these tools to save others all that trouble. Using pip and portage- gentoo's package manager-, we have installed commonly used packages that work perfectly well with each other. Just fire up a docker container, and you are good to go! If you use open source tools and python packages not installed here, please feel free to contact us/ raise an issue.


## Instructions/ Tutorial
1. Install docker
2. Download the dockerfile from the folder tutorial.
3. Install the dockerfile. This particular dockerfile will grab Python installation based on 'slim' linux distribution, and install numpy, matplotlib, and jupyter packages.
  1. Change directory to the one with the dockerfile, and firing up a terminal at the directory, type:
  docker build -t ess-minimal-stack .
  here, ess-minimal-stack is just a name you give to the image. Now, the system will start downloading the base images (if they ain't already there) and installing packages. Congrats, you have built your image.
4. Start a container. A container is an instance of the image. If you specify --rm while running the container, it will delete itself after exiting, making it analogous to a single session. If you provide it a name, you can go back to this container later. You can run the container by using docker run command, and giving the container a name, and mapping your machine's directories (which would have data/ scripts you would be working on) with the virtual directory of the container. This way, your data, scripts remain safe if you were to delete the container after use. Here we are starting a temporary container, giving it port information, as well mapping local directory (the tutorial folder) to a virtual one.
start a container by:
docker run -it -v /absolute-path-to-local-working-directory:/home/hrishi --rm -p 8888:8888 ess-minimal-stack

5. Open the test-code.ipynb. Run the code. Ensure the plot is displayed, and the figure is saved. Feel free to make changes to the script or write new scripts.
6. Terminate the container by ending the jupyter notebook session by CTRL+C. The changes made, the figures saved, will still be retained in the tutorial directory, despite deleting the container.
