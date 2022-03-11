FROM python:3.8-slim
LABEL maintainer="D.Temuujin"

# refresh SSL certificates
RUN apt-get update && apt-get install -y git curl jq ca-certificates && update-ca-certificates --fresh

# install nodejs for jupyterextension install support
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - && apt-get install -y nodejs

# Swap dash for normal bash to get more full fledged terminal session in Jupyter
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# Install Jupyter Lab
COPY ./requirements.txt .
RUN pip3 install pip --upgrade && \
    pip3 install -r requirements.txt