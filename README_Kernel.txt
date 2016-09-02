################################################################################

1. How to Build
	- get Toolchain
		From android git server , codesourcery and etc ..
		 - aarch64-linux-android-4.9

	- make output folder
		EX)OUTPUT_DIR=out
		$ mkdir out

	- edit Makefile
		edit "CROSS_COMPILE" to right toolchain path(You downloaded).
		  EX)  CROSS_COMPILE= $(android platform directory you download)/android/prebuilt/linux-x86/aarch64/aarch64-linux-android-4.9/bin/aarch64-linux-android-
          Ex)  CROSS_COMPILE=/usr/local/toolchain/aarch64-linux-android-4.9/bin/aarch64-linux-android-          // check the location of toolchain
  	
		$ export ARCH=arm64
		$ export SEC_BUILD_OPTION_HW_REVISION=02
		$ make -C $(pwd) O=$(pwd)/out KCFLAGS=-mno-android VARIANT_DEFCONFIG=msm8996_sec_hero2qlte_tmo_defconfig msm8996_sec_defconfig SELINUX_DEFCONFIG=selinux_defconfig SELINUX_LOG_DEFCONFIG=selinux_log_defconfig TIMA_DEFCONFIG=tima_defconfig DMVERITY_DEFCONFIG=dmverity_defconfig
		$ make -C $(pwd) O=$(pwd)/out KCFLAGS=-mno-android

2. Output files
	- Kernel : out/arch/arm64/boot/Image
	- module : out/drivers/*/*.ko

3. How to Clean	
		Change to OUTPUT_DIR folder
		EX) $(pwd)/out
		$ make clean
################################################################################
