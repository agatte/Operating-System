FROM randomdude/gcc-cross-x86_64-elf

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get insteall -y nasm
RUN apt-get insteall -y xorriso
RUN apt-get insteall -y grub-pc-bin
RUN apt-get insteall -y grub-common

VOLUME /root/env
WORKDIR /root/env