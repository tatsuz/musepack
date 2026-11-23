# Musepack

This repository contains the Musepack libraries and tools with some maintenance work applied to build on modern systems.

## What is Musepack?

(this section has been quoted from [the official site](https://musepack.net/).)

Musepack is an audio compression format with a strong emphasis on high quality. It's not lossless, but it is designed for transparency, so that you won't be able to hear differences between the original wave file and the much smaller MPC file.

It is based on the MPEG-1 Layer-2 / MP2 algorithms, but since 1997 it has rapidly developed and vastly improved and is now at an advanced stage in which it contains heavily optimized and patentless code.

## Copyrights

- Copyright (C) 1999-2004, Buschmann/Klemm/Piecha/Wolf
- Copyright (C) 2005-2009, The Musepack Development Team
- libreplaygain
  - Copyright (C) 2001, David Robinson and Glen Sawyer
- libcuefile has been stripped down from [cuetools](http://developer.berlios.de/projects/cuetools/).
  - Copyright (C) 2004-2006, Svend Sorensen
- wavcmp
  - Copyright (C) 2007, Nicolas Botti
- 'common' contains huffman codes generation, part of the code from the [Basic Compression Library](http://bcl.sourceforge.net/).
  - Copyright (C) 2003-2006, Marcus Geelnard
- 'common' contains [a practical implementation of the CRC](http://www.w3.org/TR/PNG/#D-CRCAppendix).
- 'win32' contains opendir() API functions for the Win32 platform.
  - Copyright (C) 2002-2006, Matthew Wilson and [Synesis Software](http://synesis.com.au/software/)
- 'win32' contains getopt() implementation by [Kannel Project](http://www.kannel.org/).
- 'win32' contains basename.c by Keith Marshall.

## Licenses

- BSD License : libmpcdec, mpc2sv8, mpccut, mpcdec, mpcgain
- GNU Lesser General Public License 2.1 or later : libmpcenc, libmpcpsy, mpcenc, libreplaygain
- GNU General Public License 2 or later : mpcchap, libcuefile
