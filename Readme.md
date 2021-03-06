This repo contains the docker-compose.yml for defining the dependencies to run the Jupyter Notebook Image described in the Dockerfile
with the Jupyterhub container described in the Dockerfile.jupyterhub.
For more details visit our website https://www.dlm.med.fau.de/setting-jupyterhub-deep-learning/


### ac edits

in this version I've:
* pruned dependencies I personally don't need (like medical imaging libraries)
* moved to the nvidia cuda 10.0/ubuntu 18.04 container, and dealt with dependency changes stemming from that
* tried to clarify the use/install process a little by adding missing `.env` variables, cleaning up config files, adding comments, etc.
* added a shared data directory for common data so users aren't storing copies of the same data
* pinned the miniconda version
* specified use of locally built deep learning notebook container

the deep learning notebook container is still super, super huge, and could stand to be paired down even more. also, the python environment is still pretty messy, with copies of the same libraries being installed by both conda and pip alongside each other. but of course cleaning those things up is hugely time intensive because you've got to rebuild the container every time you make a change.