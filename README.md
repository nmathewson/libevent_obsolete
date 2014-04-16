# 0. BUILDING AND INSTALLATION (Briefly)

## Autoconf

     $ ./configure
     $ make
     $ make verify   # (optional)
     $ sudo make install

## CMake (Windows)

Install CMake: <http://www.cmake.org>


     $ md build && cd build
     $ cmake -G "Visual Studio 10" ..   # Or whatever generator you want to use cmake --help for a list.
     $ start libevent.sln

## CMake (Unix)

     $ mkdir build && cd build
     $ cmake ..     # Default to Unix Makefiles.
     $ make
     $ make verify  # (optional)


# 1. BUILDING AND INSTALLATION (In Depth)

## Autoconf

To build libevent, type

     $ ./configure && make


 (If you got libevent from the git repository, you will
  first need to run the included "autogen.sh" script in order to
  generate the configure script.)

You can run the regression tests by running

     $ make verify

Install as root via

     $ make install

Before reporting any problems, please run the regression tests.

To enable the low-level tracing build the library as:

     $ CFLAGS=-DUSE_DEBUG ./configure [...]

Standard configure flags should work.  In particular, see:

   --disable-shared          Only build static libraries
   --prefix                  Install all files relative to this directory.


The configure script also supports the following flags:

   --enable-gcc-warnings     Enable extra compiler checking with GCC.
   --disable-malloc-replacement
                             Don't let applications replace our memory
                             management functions
   --disable-openssl         Disable support for OpenSSL encryption.
   --disable-thread-support  Don't support multithreaded environments.

## CMake (Windows)

(Note that autoconf is currently the most mature and supported build
enviroment for libevent; the cmake instructions here are new and
experimental, though they _should_ be solid.  We hope that cmake will
still be supported in future versions of Libevent, and will try to
make sure that happens.)

First of all install <http://www.cmake.org>.

To build libevent using Microsoft Visual studio open the "Visual Studio Command prompt" and type:

```
$ cd <libevent source dir>
$ mkdir build && cd build
$ cmake -G "Visual Studio 10" ..   # Or whatever generator you want to use cmake --help for a list.
$ start libevent.sln
```

In the above, the ".." refers to the dir containing the Libevent source code. 
You can build multiple versions (with different compile time settings) from the same source tree
by creating other build directories. 

It is highly recommended to build "out of source" when using
CMake instead of "in source" like the normal behaviour of autoconf for this reason.

The "NMake Makefiles" CMake generator can be used to build entirely via the command line.

To get a list of settings available for the project you can type:

```
$ cmake -LH ..
```

### GUI

CMake also provides a GUI that lets you specify the source directory and output (binary) directory
that the build should be placed in.

### OpenSSL support

To build Libevent with OpenSSL support you will need to have OpenSSL binaries available when building,
these can be found here: <http://www.openssl.org/related/binaries.html>

# 2. USEFUL LINKS:

For the latest released version of Libevent, see the official website at
<http://libevent.org/> .

There's a pretty good work-in-progress manual up at
   <http://www.wangafu.net/~nickm/libevent-book/> .

For the latest development versions of Libevent, access our Git repository
via

```
$ git clone git://levent.git.sourceforge.net/gitroot/levent/libevent
```

You can browse the git repository online at:

<http://levent.git.sourceforge.net/git/gitweb-index.cgi> 

<https://github.com/libevent/Libevent>

To report bugs, request features, or submit patches to Libevent,
use the Sourceforge trackers at

<https://sourceforge.net/tracker/?group_id=50884> 

There's also a libevent-users mailing list for talking about Libevent
use and development: 

<http://archives.seul.org/libevent/users/>

# 3. ACKNOWLEDGMENTS

The following people have helped with suggestions, ideas, code or
fixing bugs:

 * Samy Al Bahra
 * Antony Antony
 * Jacob Appelbaum
 * Arno Bakker
 * Weston Andros Adamson
 * William Ahern
 * Ivan Andropov
 * Sergey Avseyev
 * Avi Bab
 * Joachim Bauch
 * Andrey Belobrov
 * Gilad Benjamini
 * Stas Bekman
 * Denis Bilenko
 * Julien Blache
 * Kevin Bowling
 * Tomash Brechko
 * Kelly Brock
 * Ralph Castain
 * Adrian Chadd
 * Lawnstein Chan
 * Shuo Chen
 * Ka-Hing Cheung
 * Andrew Cox
 * Paul Croome
 * George Danchev
 * Andrew Danforth
 * Ed Day
 * Christopher Davis
 * Mike Davis
 * Frank Denis
 * Antony Dovgal
 * Mihai Draghicioiu
 * Alexander Drozdov
 * Mark Ellzey
 * Shie Erlich
 * Leonid Evdokimov
 * Juan Pablo Fernandez
 * Christophe Fillot
 * Mike Frysinger
 * Remi Gacogne
 * Artem Germanov
 * Alexander von Gernler
 * Diego Giagio
 * Artur Grabowski
 * Diwaker Gupta
 * Kuldeep Gupta
 * Sebastian Hahn
 * Dave Hart
 * Greg Hazel
 * Nicholas Heath
 * Michael Herf
 * Sebastian Hahn
 * Savg He
 * Mark Heily
 * Maxime Henrion
 * Michael Herf
 * Greg Hewgill
 * Andrew Hochhaus
 * Aaron Hopkins
 * Tani Hosokawa
 * Jamie Iles
 * Xiuqiang Jiang
 * Claudio Jeker
 * Evan Jones
 * Marcin Juszkiewicz
 * George Kadianakis
 * Makoto Kato
 * Phua Keat
 * Azat Khuzhin
 * Alexander Klauer
 * Kevin Ko
 * Brian Koehmstedt
 * Marko Kreen
 * Ondřej Kuzník
 * Valery Kyholodov
 * Ross Lagerwall
 * Scott Lamb
 * Christopher Layne
 * Adam Langley
 * Graham Leggett
 * Volker Lendecke
 * Philip Lewis
 * Zhou Li
 * David Libenzi
 * Yan Lin
 * Moshe Litvin
 * Simon Liu
 * Mitchell Livingston
 * Hagne Mahre
 * Lubomir Marinov
 * Abilio Marques
 * Nicolas Martyanoff
 * Abel Mathew
 * Nick Mathewson
 * James Mansion
 * Nicholas Marriott
 * Andrey Matveev
 * Caitlin Mercer
 * Dagobert Michelsen
 * Andrea Montefusco
 * Mansour Moufid
 * Mina Naguib
 * Felix Nawothnig
 * Trond Norbye
 * Linus Nordberg
 * Richard Nyberg
 * Jon Oberheide
 * John Ohl
 * Phil Oleson
 * Alexey Ozeritsky
 * Dave Pacheco
 * Derrick Pallas
 * Tassilo von Parseval
 * Catalin Patulea
 * Patrick Pelletier
 * Simon Perreault
 * Dan Petro
 * Pierre Phaneuf
 * Amarin Phaosawasdi
 * Ryan Phillips
 * Dimitre Piskyulev
 * Pavel Plesov
 * Jon Poland
 * Roman Puls
 * Nate R
 * Robert Ransom
 * Balint Reczey
 * Bert JW Regeer
 * Nate Rosenblum
 * Peter Rosin
 * Maseeb Abdul Qadir
 * Wang Qin
 * Alex S
 * Gyepi Sam
 * Hanna Schroeter
 * Ralf Schmitt
 * Mike Smellie
 * Steve Snyder
 * Nir Soffer
 * Dug Song
 * Dongsheng Song
 * Hannes Sowa
 * Joakim Soderberg
 * Joseph Spadavecchia
 * Kevin Springborn
 * Harlan Stenn
 * Andrew Sweeney
 * Ferenc Szalai
 * Brodie Thiesfield
 * Jason Toffaletti
 * Brian Utterback
 * Gisle Vanem
 * Bas Verhoeven
 * Constantine Verutin
 * Colin Watt
 * Zack Weinberg
 * Jardel Weyrich
 * Jay R. Wren
 * Zack Weinberg
 * Mobai Zhang
 * Alejo
 * Alex
 * Taral
 * propanbutan
 * masksqwe
 * mmadia
 * yangacer

If we have forgotten your name, please contact us.
