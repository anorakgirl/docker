FROM python:3.4-slim

RUN apt-get update && apt-get install -y --no-install-recommends libatlas-base-dev gfortran g++ \
                && pip install numpy && pip install scipy \
                && pip install scikit-image \
                && pip install scikit-learn && rm -Rf /root/.cache/pip \
                && apt-get remove --purge  -y gfortran g++ \
                && apt-get autoremove -y \
                && apt-get clean && rm -rf /var/lib/apt/lists/*

