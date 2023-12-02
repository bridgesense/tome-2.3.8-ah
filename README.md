Please Note
===========

This repository serves as a historical reference to ToME, rather than a platform for further development. It includes the modules 'Fury' and 'Theme', which were recovered from the Wayback Machine on Archive.org. These are remnants from the time before the original website was hacked, leading to the loss of most of the modules.

It's important to note that subsequent versions of ToME, developed by Anonymous Hero, underwent significant changes. These alterations resulted in the removal or malfunction of several features. For example, in this version, you'll notice mist in the burrow-downs which disappeared during the process of code modernization. This repository is intended to offer a glimpse into the original gameplay of ToME, preserving it as a historical reference.

Using the CMake build system
============================

There are basically two options for how to run ToME once built.



Option #1 : Run ToME from the build directory
=============================================

Simply run the commands below.

       $ cmake .
       $ make

You should now be able to run

       $ ./src/tome2

to start ToME.

This is currently the recommended option.



Option #2: Run ToME from a system install location
==================================================

Run

        $ cmake -DSYSTEM_INSTALL:BOOL=true .
        $ make
        $ sudo make install

You can now run ToME from anywhere.

You can also use DESTDIR when installing to a different location
(useful with e.g. stow or when building distribution packages).


Compiling on Ubuntu
===================

If you're having trouble compiling on an Ubuntu install you are
probably missing the

    build-essential

package.

Each frontend requires the additional packages listed below:

   X11: libx11-dev
   SDL: libsdl-image1.2-dev, libsdl-ttf2.0-dev
   ncurses: libncurses5-dev


Compiling on OpenBSD
====================

As of February 2010, the OpenBSD package cmake-2.4.8p2 is too old for
building ToME. You may need to compile a newer version of CMake.

If you have X11, then a bug in CMake may cause a linker error when
linking the 'tome' executable. As a workaround, set the environment
variable LDFLAGS=-L/usr/X11R6/lib when running CMake. Example:

       $ env LDFLAGS=-L/usr/X11R6/lib cmake .
       $ make

The SDL frontend also requires these packages: sdl-image, sdl-ttf


Compiling on Windows using MinGW
================================

(See http://www.mingw.org/)

To compile on Windows using MinGW, use the commands

       $ cmake -G "MinGW Makefiles"
       $ mingw32-make
