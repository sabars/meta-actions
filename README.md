# meta-actions Image Build

## Required packages on Ubuntu

This section provides required packages on an Ubuntu Linux distribution:

### Essentials

Packages needed to build an image for a headless system:

```shell
$ sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib \
    build-essential chrpath socat cpio python python3 python3-pip python3-pexpect \
    xz-utils debianutils iputils-ping python-git repo bmap-tools
```

## Download meta-actions project manifest

To easily manage different git repositories layers, meta-actions project is using [Android repo tool](https://source.android.com/source/using-repo),

First initialize repo specifying the project manifest and the corresponding branch:

```shell
$ repo init -u https://github.com/Linumiz/meta-actions.git/ -m conf/samples/manifest-actions.xml -b master
```

then checkout the project source tree:

```shell
$ repo sync
```

## Configuring the project

meta-actions offers pre-configured machine templates, tested and ready to use.

**Cautions**: Default machine from template is cubieboard7. The following machines are supported,
- cubieboard7
- bubblegum96

```shell
$ cd actions/
$ TEMPLATECONF=meta-actions/conf/samples/ source oe-init-build-env
```

## Build the project

```shell
$ bitbake actions-basic-image
```
