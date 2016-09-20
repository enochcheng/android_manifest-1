# nanopi_android_manifest
Nanopi manifest for marshmallow

Prerequisites
-------------
```
$ sudo apt-get install bison g++-multilib git gperf libxml2-utils make python-networkx zip
$ sudo apt-get install flex libncurses5-dev zlib1g-dev gawk minicom
```



Prepare the workspace and download sources
------------------------------------------
```
$ mkdir ~/nanopi2 && cd ~/nanopi2
$ repo init -u https://github.com/enochcheng/nanopi_android_manifest.git -b nanopi2-marshmallow
$ repo sync -jX
```
+ Replace -j**X** with number of core/cpu * 2



Set up ccache and build Android
-------------------------------
```
$ export USE_CCACHE=1
$ export CCACHE_DIR=/your/path/.ccache
$ prebuilts/misc/linux-x86/ccache/ccache -M 50G
$ source build/envsetup.sh
$ lunch aosp_nanopi2-userdebug
$ make -jX
```
+ Replace -j**X** with number of core/cpu * 2
+ Replace **/your/path/.ccache** with your preferred path



Create SD card
--------------
```
$ cd sd-fuse_nanopi2
$ ./sudo_fusing.sh /dev/sdX
```
+ Replace **X** with proper device number.
+ **For better performances uses a class 10 MicroSD card.**



#### Nanopi2 Wiki:
+ http://wiki.friendlyarm.com/wiki/index.php/NanoPi_2
