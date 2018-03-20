# Install a python installation from a 'base' linux distribution.
FROM python:3.6.2-slim

LABEL maintainer="Hrishi"

# Install python packages
RUN pip --no-cache-dir install numpy matplotlib jupyter

# Optional: Specify a working directory for the projects. 
WORKDIR /home/hrishi

#Expose a port number
EXPOSE 8888

#A default command to run each time you start a container
CMD ["jupyter", "notebook", "--ip='*'", "--port=8888", "--no-browser", "--allow-root"]

# End of Dockefile -----------------------------------
#start a container by: docker run -it --rm -p 9999:8888 ess-minimal-stack

# Once started, you can create a new jupyter notebook, run some code, print/ save outputs etc.
# example code:
# %matplotlib inline
# import numpy as np
# import matplotlib.pyplot as plt

# x = np.linspace(0, 2 * np.pi, 1000)
# y = np.sin(x)

# plt.figure()
# plt.plot(x, np.sin(y))
