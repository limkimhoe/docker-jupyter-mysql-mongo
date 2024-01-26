# See here for image contents: https://hub.docker.com/r/jupyter/datascience-notebook/

# FROM jupyter/datascience-notebook
FROM quay.io/jupyter/minimal-notebook

# Set up environment variables
ENV PYDEVD_DISABLE_FILE_VALIDATION=1
ENV JUPYTER_ENABLE_LAB=yes
ENV JUPYTER_TOKEN=SOC12345

# USER root

# Common tools and dependencies
# RUN apt-get update \
#     && apt-get install -y --no-install-recommends \
#        git \
#        build-essential \
#        libmysqlclient-dev \
#     && apt-get clean \
#     && rm -rf /var/lib/apt/lists/*

# # Switch back to jovyan to avoid running as root
# USER $NB_UID

# # Install Python dependencies
# COPY requirements.txt /tmp/
# RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY library-scripts/common-debian.sh /tmp/library-scripts/

USER root

RUN apt-get update \
 && groupadd jovyan \
 && usermod -g jovyan -a -G users jovyan \
 && bash /tmp/library-scripts/common-debian.sh \
 && apt-get clean -y && rm -rf /var/lib/apt/lists/* /tmp/library-scripts


# [Optional] If your pip requirements rarely change, uncomment this section to add them to the image.
COPY requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
   && rm -rf /tmp/pip-tmp

# [Optional] If your pip requirements rarely change, uncomment this section to add them to the image.
# COPY requirements.txt /tmp/pip-tmp/
# RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
#    && rm -rf /tmp/pip-tmp

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# Create a new Conda environment named 'myenv' with Python 3.8
# Uncomment the following lines if you need a separate conda environment
# RUN conda create --name myenv python=3.8 -y
# ENV PATH /opt/conda/envs/myenv/bin:$PATH
# RUN conda install -n myenv numpy pandas -y # Example of installing packages

# RUN conda install -n myenv notebook jupyterlab ipykernel -y
# RUN /opt/conda/envs/myenv/bin/python -m ipykernel install --user --name myenv --display-name "Python (myenv)"



USER jovyan


######################################################################

# Use the minimal Jupyter Notebook base image with Conda pre-installed
# FROM quay.io/jupyter/minimal-notebook

# # Set user to root to install additional packages
# USER root

# # Install Mamba from Conda Forge for faster package installation
# RUN conda install mamba -n base -c conda-forge

# # Create a new Conda environment named 'myenv' with Python 3.8
# RUN mamba create --name myenv python=3.8 -y
# ENV PATH /opt/conda/envs/myenv/bin:$PATH

# # Copy the requirements.txt file to the container
# COPY requirements.txt /tmp/

# # Install Python packages from requirements.txt using Mamba in 'myenv'
# # RUN mamba install -n myenv --file /tmp/requirements.txt -y
# RUN mamba install -n myenv --file /tmp/requirements.txt -vv


# # [Optional] Install additional packages in the 'myenv' environment
# # RUN mamba install -n myenv numpy pandas -y # Example of installing packages

# # Set environment variables for Jupyter
# ENV PYDEVD_DISABLE_FILE_VALIDATION=1
# ENV JUPYTER_ENABLE_LAB=yes
# ENV JUPYTER_TOKEN=SOC12345

# # [Optional] Add any custom scripts or additional setup
# # COPY library-scripts/common-debian.sh /tmp/library-scripts/
# # RUN bash -x /tmp/library-scripts/common-debian.sh \
# #    && apt-get clean -y && rm -rf /var/lib/apt/lists/* /tmp/library-scripts

# # Switch back to the jovyan user to avoid running as root
# USER jovyan

# [Optional] If you have application code, copy it to the container
# COPY . /usr/src/app
# WORKDIR /usr/src/app

# The default command to run (starts Jupyter Notebook)
# CMD ["start-notebook.sh"]
