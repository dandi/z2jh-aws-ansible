FROM jupyter/datascience-notebook:7a0c7325e470

RUN jupyter labextension install @jupyter-widgets/jupyterlab-manager
RUN pip install reactopya_jup==0.9.1
RUN jupyter labextension install reactopya_jup@0.9.1
RUN jupyter nbextension install --sys-prefix --py reactopya_jup
RUN jupyter nbextension enable reactopya_jup --py --sys-prefix

RUN pip install ephys_viz==0.9.3
RUN pip install nwbwidgets

RUN jupyter lab build

USER root
RUN mkdir /data && chown jovyan /data && chmod 777 /data && mkdir /output && chown jovyan /output && chmod 777 /output && mkdir /repos && chown jovyan /repos && chmod 777 /repos

USER $NB_USER
RUN pip install --no-cache-dir nbgitpuller
