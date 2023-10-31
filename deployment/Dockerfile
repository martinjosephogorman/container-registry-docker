FROM ubuntu:20.04

# To make it easier for build and release pipelines to run apt-get,
# configure apt to not require confirmation (assume the -y argument by default)
ENV DEBIAN_FRONTEND=noninteractive
RUN echo "APT::Get::Assume-Yes \"true\";" > /etc/apt/apt.conf.d/90assumeyes

RUN apt-get update && apt-get install -y --no-install-recommends \
    ca-certificates \
    curl \
    gnupg \
    jq \
    git \
    iputils-ping \
    libcurl4 \
    libc6 \
    libgcc1 \
    libgssapi-krb5-2 \
    libssl1.1 \
    libstdc++6 \
    wget \
    libunwind8 \
    netcat \
    libssl1.0 \
    zlib1g \
    lsb-release \
    iputils-ping \
    software-properties-common \
    python3.7 \
    python3-pip \
    apt-utils \
    zip \
    unzip \
    golang-go \
    apt-transport-https \
    && rm -rf /var/lib/apt/lists/*

COPY ./start.sh .
RUN chmod +x start.sh

ENTRYPOINT [ "./start.sh" ]