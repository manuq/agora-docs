# Integration with Sugar

## Rationale

There are several possible approaches to integrate agora with the current
Sugar implementation. Some notes about it follows. The conclusions here are
still very temptative.

It would be possible to integrate Agora inside Sugar. It might be done in 
a few ways, for example we could keep the Sugar native shell, which would talk
over D-Bus to the Agora system activity to get a list of installed activities
and activate them when necessary.

It would be possible to integrate Sugar activities inside Agora. Again it
might be done in a few ways, for example we could use the html5 gtk backend
to display gtk activities in Agora.

Supporting both native and web activities is problematic

* Native activities does not currently in a sandbox so unlike web activities
they can easily be a security threat. We could use some kind of containers,
but it's really not trivial.
* If we want web activities to work everywhere their UI will have to be
written entirely using HTML. This means that we will need to maintain
forever two implementations of the Sugar UI controls.
* While there a lot of possible approaches to integrate the two worlds, all of
them seems to be tricky and not fully satisfactory.

Taking a step back, the final goal here should be to write all the new 
activities using web technologies. So perhaps it's worth to focus on a
migration path rather then an integration one. If we gave developers the
possibility to write web applications and easily generate native xo bundles
from them, that might the quickest way to begin the migration.

## Current implementation

There is a very initial implementation of this approach in the
[agora-sugar](https://github.com/ayopa/agora-sugar) repository. Just add
your own activity as a submodule.

First pull all the sources

    git submodule update --init

The add your own web application to the repository. For example

    git submodule add git://github.com/ayopa/omega-gridpaint.git

Finally build it

    ./build.py

The xo files are in the build directory.

## Future work

* The ability to develop activities only in Linux has been a limiting factor
for Sugar. On the short time the role of Agora might that of a cross platform
development environment for Sugar. In fact it will easily build in mac os
and hopefully windows. People might test activities there and than just
run the conversion script to generate a xo.
* The conversion script is very basic, just demonstrative really. The logic
is very simple though, it should be easy to extend it as necessary.
* This will be a lot more interesting as soon as we will have a reasonably
complete implementation of xi-graphics and a sugar implementation of
xi-datastore and xi-collaboration. At that point it will be possible to write
web applications that will feel exactly like a native activity when running
inside sugar.
* The easiest way to implement the xi API for Sugar is probably to send
messages to the native python activity implementation.
