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
