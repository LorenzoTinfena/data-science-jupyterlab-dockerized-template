FROM jupyter/datascience-notebook:latest

# update conda packages
RUN conda update --yes --all

# install requirements
ADD ./conda_requirements.txt /tmp/
RUN conda install --force-reinstall --yes --file /tmp/conda_requirements.txt

# install jupyter lab extensions
# add here your favourite labextensions!
RUN jupyter labextension install --no-build -y @jupyterlab/debugger

RUN jupyter lab build

EXPOSE 8888
ENV RESTARTABLE=yes

# uncomment to use jupyterlab, but jupyter_contrib_nbextensions won't work
ENV JUPYTER_ENABLE_LAB=yes

# uncomment to get root access
#ENV GRANT_SUDO=yes