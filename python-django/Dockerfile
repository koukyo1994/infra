FROM python:3.7

RUN apt-get update -y && \
    apt-get install -yq \
    wget build-essential gcc zlib1g-dev apt-utils make curl \
    git xz-utils file swig sudo software-properties-common \
    locales

RUN locale-gen ja_JP.UTF-8 && \
    echo "export LANG=ja_JP.UTF-8" >> ~/.bashrc

RUN python3.7 -m pip install pip --upgrade

ADD . /app
WORKDIR /app

RUN pip install -r requirements.txt

EXPOSE 8000
CMD ["/bin/bash"]
