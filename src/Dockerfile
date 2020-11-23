FROM jupyter/datascience-notebook:latest

# update conda packages
RUN conda update --yes --all

# install requirements
ADD ./requirements.txt /tmp/
RUN conda install --force-reinstall --yes --file /tmp/requirements.txt

# configure jupyter lab extensions
RUN conda install --yes jupyter_contrib_nbextensions
RUN jupyter contrib nbextension install --user
RUN jupyter nbextension enable hinterland/hinterland

EXPOSE 8888

# uncomment to use jupyterlab, but jupyter_contrib_nbextensions won't work
#ENV JUPYTER_ENABLE_LAB=yes

# uncomment to get root access
#ENV GRANT_SUDO=yes