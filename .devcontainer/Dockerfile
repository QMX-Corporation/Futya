# SPDX-License-Identifier: GPL-2.0-Only

FROM debian:stable-slim

RUN apt-get update && apt-get install --no-install-recommends -y \
            git \
            make \
            gcc-aarch64-none-elf \ 
            binutils-aarch64-none-elf \
            openjdk-17-jdk-headless \
            && rm -rf /var/lib/apt/lists/*
             

WORKDIR /workspace

CMD ["bash"]