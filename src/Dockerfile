FROM jupyter/datascience-notebook:latest

ADD ./requirements.txt /tmp/

RUN conda update --yes --all
RUN conda install --force-reinstall --yes --file /tmp/requirements.txt

RUN conda install jupyter_nbextensions_configurator

RUN conda install jupyter_contrib_nbextensions
RUN jupyter contrib nbextension install --user
#TODO abilita le estensioni da qua e fa che workino

EXPOSE 8888
ENV JUPYTER_ENABLE_LAB=yes

#ENV GRANT_SUDO=yes