# hash:sha256:0f20739378690b253837d52190fc6df05283c00105021f0fc1764bf97a4b6d32
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/swdb:Python3.12code-server4.133

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
    scipy==1.18.0
