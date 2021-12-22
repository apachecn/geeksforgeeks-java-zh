# 用 5 个简单的步骤编译我们自己的安卓内核

> 原文:[https://www . geeksforgeeks . org/编译-我们自己的-安卓-5 步内核-简单/](https://www.geeksforgeeks.org/compile-our-own-android-kernel-in-5-simple-steps/)

[安卓内核](https://www.geeksforgeeks.org/introduction-to-android-development/)帮助应用程序与设备的硬件组件进行通信。

比如:

1.  Most of us are familiar with **game mode** . Its function is to instruct the processor and graphics processing unit to run at the maximum frequency.
2.  Another example is **power saving mode** . It instructs the processor and graphics processing unit to run at their minimum frequency.

<u>**需要编译我们自己的内核:**</u> 编译我们自己的内核可能会非常有用，因为:

*   Use our own kernel.
*   The user experience can be further optimized as needed, which is also helpful for [open source development](https://www.geeksforgeeks.org/contributing-to-open-source-getting-started/) .

<u>**编译我们自己的内核的步骤:**</u>

1.  **Prerequisites:** The following are prerequisites for compiling our own Android kernel:
    *   [Ubuntu or any other Linux-based OS](https://www.geeksforgeeks.org/introduction-to-linux-operating-system/)
    *   Familiar with [basic Linux command](https://www.geeksforgeeks.org/linux-commands/)
    *   阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金·阿金 [Github](https://www.geeksforgeeks.org/ultimate-guide-git-github/)
    *   Equipment [Source code [T2】 T30 Open the terminal and paste it as follows:

        ```java
        sudo apt-get install
             git ccache automake flex lzop bison \
             gperf build-essential zip curl
                 zlib1g-dev zlib1g-dev:i386 \
             g++-multilib python-networkx 
                 libxml2-utils bzip2 libbz2-dev \
             libbz2-1.0 libghc-bzlib-dev 
                 squashfs-tools pngcrush \
             schedtool dpkg-dev liblz4-tool 
                 make optipng maven libssl-dev \
             pwgen libswitch-perl policycoreutils 
                 minicom libxml-sax-base-perl \
             libxml-simple-perl bc
                 libc6-dev-i386 lib32ncurses5-dev \
             x11proto-core-dev libx11-dev 
                 lib32z-dev libgl1-mesa-dev xsltproc unzip
        ```](https://www.geeksforgeeks.org/language-processors-assembler-compiler-and-interpreter/) 
    *   **Download required documents:**
        *   Clone the device source on the local disk:

            ```java
            mkdir mykernel
              git clone {link to your device kernel source}
            ```

        *   Download a compatible [GCC](https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/) tool chain. In this paper, GCC of AOSP is used.

            ```java
            cd mykernel
               git clone https://android.googlesource.com/platform/
                         prebuilts/gcc/linux-x86/aarch64/
                         aarch64-linux-android-4.9
               toolchain
            ```

        *   Download a compatible CLANG tool chain. This paper uses Clang of [AOSP.](https://android.googlesource.com/platform/prebuilts/clang/host/linux-x86/+archive/android-9.0.0_r48/clang-4691093.tar.gz)
        *   Move the downloaded file to the **mykernel folder** , and then use the following command to extract it:

            ```java
            tar vxzf linux-x86-android-9.0.0_r48-clang-4691093.tar.gz
            ```

    *   **编译内核:**

        ```java
        cd mykernel
        rm -rf out
        mkdir out
        export ARCH=arm64
        export SUBARCH=arm64
        export DTC_EXT=dtc

        make O=out ARCH=arm64 {device defconfig}

        PATH="${PWD}/bin:${PWD}/toolchain/bin:${PATH}" \
        make -j$(nproc --all) O=out \
                              ARCH=arm64 \
                              CC=clang \
                              CLANG_TRIPLE=aarch64-linux-gnu- \
                              CROSS_COMPILE=aarch64-linux-android-
                              | tee kernel.log
        ```

        在这里，将{device defconfig}替换为您的配置文件的名称。您可以在/arch/arm64/configs 文件夹中找到它。

    *   **Boot the compiled kernel:**
        *   Browse to **/out/arch/ARM64/boot** , find **image-DTB file** (compiled zImage) and copy it.
        *   Download [Android mirror kitchen](https://forum.xda-developers.com/showthread.php?t=2073775) and decompile your stock boot image. Once you decompile it, you will find the stock code in the decompiled folder. Replace it with the previously copied one and recompile the boot image.
        *   Flash [Fast boot](https://dl.google.com/android/repository/platform-tools-latest-linux.zip) uses the following commands:

            ```java
            fastboot flash boot mykernel.img
            ```

    *   **Error encountered in processing:** A kernel.log file will be generated in mykernel folder. Find the wrong line and find a solution. Also, please don't forget to attach the log file when posting for help in the forum.

这将是基本的内核，一旦它成功启动，可以添加更多的功能。