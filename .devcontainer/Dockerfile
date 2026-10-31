# SPDX-License-Identifier: GPL-2.0-Only

FROM debian:stable-slim

RUN apt-get update && apt-get install --no-install-recommends -y \
            git \
            gas \
            make \
            gcc-aarch64-none-elf \ 
            binutils-aarch64-none-elf
             

WORKDIR /workspace

CMD ["bash"]