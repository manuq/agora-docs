# About

Agora is an attempt to achieve the goals of the
[Sugar Learning Platform](http://sugarlabs.org/) using the web technologies.

# Motivations

* Using cross platform development tools allows us to run on a variety of
software platforms and hardware devices. In particular it give us access to
tablets and phones, without having to build our own OS.
* Web technologies allows a wide expressivity and makes integration with content seamless. They are also very actively developed and widely known.

# Architecture

It's important to point out that many of components described here already
exists as part of other projects. In particular we borrow heavily from the
Mozilla's platform.

## Eta

Eta is a set of python scripts which will take care of building the Agora
components and package them up as an application or a full system image.

## Sigma

Sigma is the base system. Implementations might differ greatly depending on
the hardware and software of choice. It may run as a standalone image or on
the top of other systems like Linux or OS X.

### Common elements

* [b2g](http://wiki.mozilla.org/B2G)

    Here we are referring to the application built on the top of Gecko, not
    to the whole Firefox OS. It provides a platform to run web applications.
    Some implementations might include extensions to b2g, that allows to
    interact with native system components.

* [node](http://nodejs.org/)

    At the moment it's required just as a dependency of volo.

* [volo](http://volojs.org/)

    It's a development tool used by the Xi libraries and the Omega activities.
    It automates depedency management for JavaScript projects.

### Ports (in progress)

* Linux

    It's based on a typical Linux distribution.

### Ports (planned)

* Gonk

    It's based on Mozilla's Gonk, which is based on Android. The main benefit
    is that it allows to run Agora on mobile devices.

## Xi

Xi is a collection of JavaScript libraries which ensures UI consistency and
provides an abstract interface to interact with local or remote services. The
line between native and cross platform code lies just above it.

### In progress

* xi-activity

    A template of an activity.

* xi-artwork

    A set of icons, with code to load and manipulate them.

### Planned

* xi-graphics

    A set of UI controls. Toolbars, buttons and so on.

* xi-datastore

    An interface to store and query activities data.

* xi-collaboration

    An interface to nuild collaborative activities.

## Omega

Omega is a collection of open web applications. In user speech they goes
under the name of activities and together they form the Agora user experience.

### In progress

* omega-system

    It provides system components like the home and activity management.

* omega-browse

    A web browser.

* omega-terminal

    A text terminal.
