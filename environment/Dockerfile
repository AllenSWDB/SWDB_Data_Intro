# hash:sha256:a11ce7b70994ed36371075c3c70d140543c4921a90224281c141a40772f32acd
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/code-server-python-extensions-pack:code-server4.129.0python3.12.4codeocean-mcp-serveruvpyreflyetc

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN conda install -y \
        jupyterlab==4.6.3 \
    && conda clean -ya

RUN pip3 install -U --no-cache-dir \
    hdmf-zarr==0.12.0 \
    matplotlib==3.10.1 \
    numpy==2.2.5 \
    pandas==2.2.3 \
    pynwb==3.1.3
