1. Android build
  - Download original android source code ( M 6.0.1 ) from http://source.android.com
  - Untar opensource packages of LGLS775_M_Android.tar.gz into downloaded android source directory
       a) tar -xvzf LGLS775_M_Android.tar.gz
  - And, merge the source into the android source code
  - Run following scripts to build android
    a) source build/envsetup.sh
    b) lunch 1
    c) make -j4
  - When you compile the android source code, you have to add google original prebuilt source(toolchain) into the android directory.
  - After build, you can find output at out/target/product/generic

2. Kernel Build  
  - Uncompress using following command at the android directory
        a) tar -xvzf LGLS775_M_Kernel.tar.gz

  - When you compile the kernel source code, you have to add google original prebuilt source(toolchain) into the android directory.
  - Run following scripts to build kernel
    a) cd kernel
	  b) make ARCH=arm64 ph1_spr-perf_defconfig
		c) make ARCH=arm64 CROSS_COMPILE=../prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9/bin/aarch64-linux-android- -j4
	
	* "-j4" : The number, 4, is the number of multiple jobs to be invoked simultaneously. 
  - After build, you can find the build image(Image.gz) at arch/arm64/boot
