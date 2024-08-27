# Use the official Jupyter Notebook image
FROM jupyter/base-notebook:latest

# Set the working directory
WORKDIR /home/jovyan/work

# Switch to the root user
USER root

# Initialize Conda for the root user
RUN /opt/conda/bin/conda init bash

# Set the entrypoint to start Conda
ENTRYPOINT ["/bin/bash", "-c", "source /root/.bashrc && jupyter notebook --ip=0.0.0.0 --no-browser --allow-root"]
