**Setup**

Build an image for our build-environment

    docker build buildenv -t myos-buildenv

**Build**

Enter build environment

    Linux or MacOS: docker run --rm -it -v "$pwd":/root/env myos-buildenv
    Windows (CMD): docker run --rm -it -v "%cd%":/root/env myos-buildenv
    Windows (Powershell): docker run --rm -it -v "${pwd}:/root/env" myos-buildenv
    NOTE: If you are having trouble with an unshared drive, ensure your docker daemon has access to the drive you're development environment is in. For Docker Desktop, this is in "Settings > Shared Drives" or "Settings > Resources > File Sharing". 

Build for x86 (other architectures may come in the future):

    make build-x86_64

To leave the build environment, enter exit

**Emulate**

You can emulate your operating system using Qemu (Don't forget to add gemu to your path!)

    qemu-system-x86_64 -cdrom dist/x86_64/kernal.iso
    NOTE: When building your operating system, if changes to your code fail to compile, ensure your QEUMU emulator has been closed, as this will block writing to kernal.iso

Alternatively, you should be able to load the operating system on a USB drive and boot into it when you turn on your computer. (I have not tested this yet).

**Cleanup**
