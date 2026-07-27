# hash:sha256:04753f7fbf9d4b2a4addeb485842dd8bf5cce591895705c33a9e08626ada8d2e
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/code-server-python-extensions-pack:code-server4.129.0python3.12.4codeocean-mcp-serveruvpyreflyetc

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN pip3 install -U --no-cache-dir \
    matplotlib==3.10.1 \
    numpy==2.2.5 \
    pandas==2.23 \
    pynwb==3.1.3
