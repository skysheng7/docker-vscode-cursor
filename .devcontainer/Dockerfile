# build on top of template of minimal notebook
FROM mcr.microsoft.com/devcontainers/base:ubuntu

# copy all conda environment dependencies
COPY conda-lock.yml /tmp/conda-lock.yml

# conda install all the other packages
RUN mamba update --quiet --file /tmp/conda-lock.yml \
    && mamba clean --all -y -f \
    && fix-permissions "${CONDA_DIR}" \
    && fix-permissions "/home/${NB_USER}"