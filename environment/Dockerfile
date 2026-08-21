# hash:sha256:ad626e5938910fdb5f821838928a554c3e7d8782cff2777b851b96b0bc5298fa
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
    pynwb==4.0.0
