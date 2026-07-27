# hash:sha256:bda8be6cceea38689a91510b7c1e084e7d3f0bf549ffb1a5c82e6ba9441bc0c4
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/code-server-python-extensions-pack:code-server4.129.0python3.12.4codeocean-mcp-serveruvpyreflyetc

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN pip3 install -U --no-cache-dir \
    hdmf-zarr==0.12.0 \
    matplotlib==3.10.1 \
    numpy==2.2.5 \
    pandas==2.2.3 \
    pynwb==3.1.3
