meta-bitmainer
=============

OpenEmbedded / Ångström meta layer for bitminer Miner

Setup instructions
------------------

To build a bitmainer miner firmware, first prepare a build machine as per OpenEmbedded Required software instructions at http://www.openembedded.org/wiki/Getting_started

When machine is prepared proceed to prepare the bitmainer firmware build by running

    git clone https://github.com/jeffpcyo/setup-A8
    cd setup-A8
    MACHINE=beaglebone ./oebb.sh config beaglebone

Rootfs build instructions
----------------------------------

To build the firmware rootfs run

    . environment-angstrom-v2013.06
    ./build-ltc.sh L3/L3+(Miner type) 384(Freq) [init](Only for the first time.)

and then wait for quite a bit for the build to complete.

Note: You will need ~11GB free disk space.

The resulting root initramfs will be in

    setup-A8/deploy/eglibc/images/beaglebone/Angstrom-bitmainer-eglibc-ipk-v2013.06-beaglebone.rootfs.cpio.gz.u-boot


Kernel build instructions
-----------------------------------

To build the Linux kernel image run

    . environment-angstrom-v2013.06
    bitbake virtual/kernel

which results in a kernel image at

    setup-A8/deploy/eglibc/images/beaglebone/
