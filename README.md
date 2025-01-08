# BITCOIN WALLET

Welcome to _Bitcoin Wallet_, a standalone Bitcoin payment app for your Android device!

This project contains several sub-projects:


### PREREQUISITES FOR BUILDING

You'll need git, a Java 17 SDK and Gradle 4.4 for this
download gradle 4.4 from this [link]
{https://gradle.org/next-steps/?version=4.4&format=bin}
Create a directory for the Android SDK (e.g. `android-sdk`) and point the `ANDROID_HOME` variable to it.

Download the [Android SDK Tools](https://developer.android.com/studio/index.html#command-tools)

### BUILDING

You can build all sub-projects in all flavors at once using Gradle:

    # each time
    gradle clean build

For details about building the wallet see the [specific README](wallet/README.md).


### REPRODUCIBLE BUILD

Alternatively, you can build using buildah:

    # each time
    buildah build --cap-add sys_admin --device /dev/fuse --file build.Containerfile --output build/ .

Access to FUSE and the SYS_ADMIN capability are needed for mounting disorderfs
in order to sort the directory entries of the project folder.

The unsigned APKs are written to the specified output directory.
