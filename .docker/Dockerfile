# syntax = docker/dockerfile:1.2
FROM mkrausio/ml_research:uv42

ARG COMPOSE_PROJ_NAME="project_name"

ENV PROJECT_NAME=${COMPOSE_PROJ_NAME}
RUN echo ${COMPOSE_PROJ_NAME}/$PROJECT_NAME

RUN apt update -y && apt upgrade -y && apt install unzip

RUN curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash && \
  apt-get install -y git-lfs

RUN mkdir -p workspaces/$PROJECT_NAME
WORKDIR /workspaces/$PROJECT_NAME


RUN pip install uv

ENV PYTHONPATH=$PYTHONPATH:src

CMD zsh
