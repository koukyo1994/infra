FROM python:3.7

RUN apt-get update -y && \
    apt-get install -yq wget build-essential gcc zlib1g-dev && \
    apt-get install -y apt-utils mecab libmecab-dev make curl && \
    apt-get install -yq git xz-utils file swig sudo software-properties-common

RUN git clone --depth 1 https://github.com/neologd/mecab-ipadic-neologd.git \
    && cd mecab-ipadic-neologd \
    && bin/install-mecab-ipadic-neologd -n -y

RUN apt-get update \
    && apt-get install -y locales \
    && locale-gen ja_JP.UTF-8 \
    && echo "export LANG=ja_JP.UTF-8" >> ~/.bashrc

RUN python3.7 -m pip install pip --upgrade

CMD ["/bin/bash"]
