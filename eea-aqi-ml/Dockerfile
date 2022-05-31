FROM python:3.8-slim-buster

RUN apt-get update
RUN apt-get install -y build-essential cmake git unzip pkg-config libopenblas-dev liblapack-dev libhdf5-dev python3-dev python3-pip

RUN pip3 install pip
RUN pip3 install --upgrade pip
# RUN sudo pip3 install setuptools
RUN python3 -m pip install python-dateutil tensorflow pandas nbformat scipy matplotlib 'h5py<3.0.0' graphviz pydot-ng opencv-python keras plotly sklearn csv-to-json azure-storage-blob azure-storage-file-share azure-storage-file-datalake azure-batch ciso8601 joblib silence_tensorflow fancyimpute pytz boto3 pyarrow

# Opcional para parsear rasters
RUN apt-get install -y gdal-bin python3-gdal libeccodes-dev libgdal-dev

# azcopy
COPY azcopy /usr/bin/
RUN python3 -m pip install gdal==2.4.0

# más pips, pero después para aprovechar la caché
RUN python3 -m pip install azure-data-tables

RUN python3 -m pip install tweepy
