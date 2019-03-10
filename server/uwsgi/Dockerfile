## Base Python image for building uWSGI
FROM python:3.7.2-slim-stretch as builder

# Install some basic tools
RUN apt-get update && apt-get -y install \
    build-essential

# Building uWSGI
COPY dynamic/python/requirements.txt .
RUN pip install $(grep uWSGI requirements.txt)

## Base Python image for final image
FROM python:3.7.2-slim-stretch

# Get python packages from previous build stage
ARG PYTHON_VERS=python3.7
WORKDIR /usr/local/lib/${PYTHON_VERS}/site-packages/
COPY --from=builder /usr/local/lib/${PYTHON_VERS}/site-packages/ .

# Get compiled uWSGI executable from previous build stage
COPY --from=builder /usr/local/bin/uwsgi /usr/local/bin/uwsgi

# Change workdir
WORKDIR /usr/local/src

# Get python source
COPY dynamic .

# Get rest of requirements
RUN pip install $(grep -v uWSGI python/requirements.txt | tr '\n' ' ')
