################################################################################
1. Download and unzip the kernel source of A045MUBU4DXA5.

2. Unzip and update the kernel source of A045MUBS6DXF1.

3. How to Build
        - get Toolchain
                From android git server, codesourcery and etc ..
                - clang/host/linux-x86/clang-r383902/bin/aarch64-linux-gnu-
        - edit Makefile
                edit "CROSS_COMPILE" to right toolchain path(You downloaded).
                        EX)  CROSS_COMPILE=<android platform directory you download>/android/prebuilts/clang/host/linux-x86/clang-r383902/bin/aarch64-linux-gnu-
                        EX)  CROSS_COMPILE=/usr/local/toolchain/clang/host/linux-x86/clang-r383902/bin/aarch64-linux-gnu- // check the location of toolchain
                edit "CLANG" to right path(You downloaded).
                        EX)  CC=<android platform directory you download>/android/prebuilts/clang/host/linux-x86/clang-r383902/bin/clang
                        EX)  CC=/usr/local/toolchain/clang/host/linux-x86/clang-r383902/bin/clang // check the location of toolchain
                edit "CLANG_TRIPLE" to right path(You downloaded).
                        EX)  CLANG_TRIPLE=<android platform directory you download>/android/prebuilts/aarch64-linux-gnu-
                        EX)  CLANG_TRIPLE=/usr/local/toolchain/aarch64-linux-gnu- // check the location of toolchain     
        - to Build
                $ export ANDROID_MAJOR_VERSION=r
                $ export ARCH=arm64
                $ make -C $(pwd) O=$(pwd)/out KCFLAGS=-w CONFIG_SECTION_MISMATCH_WARN_ONLY=y a04_defconfig
                $ make -C $(pwd) O=$(pwd)/out KCFLAGS=-w CONFIG_SECTION_MISMATCH_WARN_ONLY=y

4. Output files
        - Kernel : arch/arm64/boot/Image.gz
        - module : drivers/*/*.ko

5. How to Clean
        $ make clean
################################################################################
