# hash:sha256:f0122a5cd6225acc43797e6f2a651ac398bcd4a562a1672a1edb6b09b1d1a0f1
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/code-server-python-extensions-pack:code-server4.129.0python3.12.4codeocean-mcp-serveruvpyreflyetc

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN pip3 install -U --no-cache-dir \
    matplotlib==3.10.1 \
    numpy==2.2.5 \
    pandas==2.2.3 \
    pynwb==3.1.3
