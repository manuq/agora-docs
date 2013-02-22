# Prerequisites

So far agora has been tested on

Fedora 18 (64-bit)
Debian Wheezy (64-bit)

It probably works also on Ubuntu 12.10 (64-bit). If you can choose, Fedora 18
is, at the moment, the one which is more likely to work out of the box.

Before starting make sure git, python3, yum and curl are installed.

# Build

First clone the agora repository

    git clone git://github.com/ayopa/agora.git

Bootstrap the environment

    cd agora
    ./agora.py bootstrap

Then pull the sources

    ./agora.py pull

Build them

    ./agora.py build

And finally run agora

    ./agora.py run

## Options

You can configure eta, the build system, edit the config.json file in the agora
root directory.

* build_type. By default we try to choose the best build type for the system,
but there are cases where you might want to override it. Currently we support

    * linux. Build agora on the top of a linux distribution. At the moment only
    the latest version of Fedora is supported.
    * chroot. Build agora inside a Fedora 18 chroot. This should work on any
    recent x86_64 linux distribution.

Here is an example config.json

    {"build_type": "chroot"}

# Create a new activity

You need to enter the development shell first

    ./agora shell

Then setup an activity project using volo

    volo create omega/helloworld ayopa/omega-activity

To add one of the xi libraries you can use the volo add command

    volo add apoya/xi-artwork

If you build and run agora, you should see the new activity

    ./agora build
    ./agora run
