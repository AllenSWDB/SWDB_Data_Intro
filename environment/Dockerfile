# hash:sha256:202b61f027a9d0f37582a0a7201ca7a3a39326b7160680a24cfe8c37db56e211
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/code-server-python-extensions-pack:code-server4.129.0python3.12.4codeocean-mcp-serveruvpyreflyetc

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN conda install -y \
        jupyterlab==4.6.3 \
    && conda clean -ya

RUN pip3 install -U --no-cache-dir \
    aind-data-access-api==1.2.1 \
    hdmf-zarr==0.12.0 \
    matplotlib==3.10.1 \
    numpy==2.2.5 \
    pandas==2.2.3 \
    pynwb==4.0.0 \
    scipy
