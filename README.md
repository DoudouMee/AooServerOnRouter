# AooServerOnRouter

Aooserver Cross Compiled for *MIPS* and *ARM64*  OpenWRT router.

Source code https://github.com/essej/aooserver

The library files and executables of these two architectures are compiled using [openwrt-sdk-21.02.3-rockchip-armv8_gcc-8.4.0_musl.Linux-x86_64](https://downloads.openwrt.org/releases/21.02.3/targets/rockchip/armv8/openwrt-sdk-21.02.3-rockchip-armv8_gcc-8.4.0_musl.Linux-x86_64.tar.xz) and [openwrt-sdk-21.02.3-ramips-mt7621_gcc-8.4.0_musl.Linux-x86_64](https://downloads.openwrt.org/releases/21.02.3/targets/ramips/mt7621/openwrt-sdk-21.02.3-ramips-mt7621_gcc-8.4.0_musl.Linux-x86_64.tar.xz) respectively.



They have been test work well on **MT7621**(MIPS) and **RK3328**(ARM64) **Openwrt** router.

To use it on an openwrt router, putting the library files into path like `/usr/lib` if needed.

> You need to get *mips_lib.tar.gz*  or *arm_lib.tar.gz*  unzipped and place files into your dependent directory, such as `/usr/lib`.
>
> Maybe different release of openwrt depend on different library files. Better to just put in the library files it needs.
>
> Using command `ldd -file` to find what dependencies are you missing.



# NOTE

To build an *aooserver* of your own device from source https://github.com/essej/aooserver. 

You may need **comment out** *line 96*  in `JuceLibraryCode/modules/juce_core/juce_core.cpp`.

> ```c
>  #if ! JUCE_ANDROID
>   //#include <execinfo.h>
>  #endif
> ```

You may also need to build your own library files first, such as *libcurl*, *libnghttp2*. 

After that **change the makefile** and add these dependencies into it.
