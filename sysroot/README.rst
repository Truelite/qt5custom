==============================================================================
Building and packaging a sysroot for Qt5 cross-development for Raspberry Pi OS
==============================================================================

This package prepares a Raspberry Pi OS filesystem with preinstalled all
dependencies needed to build a Qt5 cross-build environment that includes
QtWebEngine, and packages it in ``/opt/qt5-raspios-sysroot``.

It is needed both as a build dependency to build the cross-builder, and as a
dependency while cross-developing with it.

To build the package:

1. install its ``Build-Depends``
2. download a Raspberry Pi OS Lite image and extract it from its ``.zip`` file
3. set ``RASPIOS_IMAGE`` in ``debian/rules`` to point to the resulting ``.img``
   file
4. ``sudo debian/rules binary``

Building requires root, to access the image, mount its file systems, create an
emulated armhf container, and run commands inside it to install the packages it
needs.
