# Lineage buildscripts
========================

First I recommend checking the official LineageOS wiki instructions for building for hiphi here to see what are the dependencies and how to install them
https://wiki.lineageos.org/devices/hiphi/build

Also please note that repopick.sh isn't always updated. Please check LineageOS Gerrit in case there is changes to repopick topics.

Starting from zero:
---------
    # cd into your ROM's folder (IE, from scratch I would mkdir -p ~/android/lineage-23.2 && cd ~/android/lineage-23.2)
    repo init -u https://github.com/LineageOS/android.git -b lineage-23.2 --git-lfs
    mkdir -p .repo/local_manifests
    curl https://raw.githubusercontent.com/motorola-sm8450-devs/local_manifests/rebase2/lineage-23.2/motorola-common.xml > .repo/local_manifests/motorola-common.xml
    curl https://raw.githubusercontent.com/motorola-sm8450-devs/local_manifests/rebase2/lineage-23.2/motorola-sm8475.xml > .repo/local_manifests/motorola-sm8475.xml
    repo sync

If you've already synced Lineage-Sources:
----------
    # cd into your ROM's folder
    mkdir -p .repo/local_manifests
    curl https://raw.githubusercontent.com/motorola-sm8450-devs/local_manifests/rebase2/lineage-23.2/motorola-common.xml > .repo/local_manifests/motorola-common.xml
    curl https://raw.githubusercontent.com/motorola-sm8450-devs/local_manifests/rebase2/lineage-23.2/motorola-sm8475.xml > .repo/local_manifests/motorola-sm8475.xml

Building
----------
    # cd into your ROM's folder
    curl https://raw.githubusercontent.com/motorola-sm8450-devs/local_manifests/rebase2/lineage-23.2/hiphi_clean_build.sh > hiphi_clean_build.sh
    curl https://raw.githubusercontent.com/motorola-sm8450-devs/local_manifests/rebase2/lineage-23.2/hiphi_dirty_build.sh > hiphi_dirty_build.sh
    ./hiphi_clean_build.sh // for hiphi clean builds
    ./hiphi_dirty_build.sh // for hiphi dirty builds

I made these modified scripts for convenience plus logs terminal output to files for easy scrolling later in your favorite text editor.
