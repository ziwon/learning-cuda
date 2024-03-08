# https://gitlab.com/nvidia/container-images/cuda/-/blob/master/dist/12.3.2/ubuntu2204/base/Dockerfile
FROM nvidia/cuda:12.3.2-cudnn9-devel-ubuntu22.04

ENV TZ=Asia/Seoul
ENV PYTHONUNBUFFERED=1

RUN apt-get update \
    && apt install -y git wget ubuntu-drivers-common \
    && apt install -y nvidia-cuda-toolkit \
    && apt install -y --no-install-recommends python3.10-dev python3-pip \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# RUt git clone https://github.com/TimDettmers/bitsandbytes.git \
#     && cd bitsandbytes \
#     && bash install_cuda.sh 123 ~/.local 1

ENV PATH="/root/.local/bin:$PATH"

WORKDIR /workspace

COPY . .

RUN pip install --no-cache-dir -r requirements.txt
