#######
NOTICE!
#######

**This project/library was formerly known as Cairocks!** If you are
looking for it (*for example, if your Git remote just ... broke*) then look no
further; it is here!

######
Cairou
######

A small library of useful, common Cairo routines. It aims to be for Cairo what
libGLU was for traditional OpenGL.

Overview
========

.. _named-path: https://github.com/cubicool/cairou/blob/master/src/named-path.cpp
.. _text: https://github.com/cubicool/cairou/blob/master/src/text.cpp

Cairou (Cairo Utility) was born from a common codebase I continually ended up
copying from project to project. Instead of trying to keep all these different
versions in sync, I've decided to divorce it out into its own project and
maintain it thusly. It is written using a mix of C90-compatible C and C++03,
although it strictly maintains a C-linkable API for maximum accessibility. C++
is usually only used (see `text`_ and `named-path`_) to take advantage of the
STL.

While Cairou does include an example build system using CMake, you are
welcome to include the source wholesale into your own projects. Additionally,
I have provided an example Python extension module demonstrating Cairou's usage
when paired with the fantastic cairocffi project.

Enjoy! AND PLEASE, contribute your own little tidbits of useful stuff!

A special thanks to the following people

* Behdad Esfahbod
* Mirco Mueller
* John Schlag, "Graphics Gems IV"
* ranma42, pippin, joonas (Andrea Canciani, Oyvind Kolas, M. Joonas Pilhaja) in IRC;
  so much fantastic help from a great community

License
=======

There is no strict license accompanying Cairou, and the code I have borrowed
from others (that is, that code I did not write myself) was all released with
no license of any kind.  However, I encourage you to do unto others...

Features
========

.. _Glyphicons: http://glyphicons.com

* Generate "unsigned distance field" surfaces (as popularized by Valve).
* Emboss, gaussian blur, and surface inversion filters.
* Support for loading image surfaces from GIF files (with access to each individual
  GIF frame).
* Support for loading image surfaces from JPEG images.
* A useful wrapper for loading PNG images from memory.
* An API wrapping and simplifying using the `Glyphicons`_ font, with support
  for interchangable icon backends in the future.
* Drastically simplified text functions wrapping the Cairo "toy" API with support
  for multiple lines and advanced XY positioning (based on the extents of the entire
  body of text).
* Support for splines (by creating large groups of 2D points as control structures).
* Map paths onto other paths; for example, rendering text along arcs, etc.
* Introduces the concept of context-specific, persistent "named paths", which can be
  used to push and pop saved (named) paths to and from the associated context.

TODO
====

* Harfbuzz layout support.
* Spline constraints; i.e., point x0 must stay 5 units perpendicular to point x1
  at all times.
* Add rounded_rectangle method that accepts a center position and radius.
* Add cairou_object_path/cairou_show_object.
* Implement cairou_state_t structure, or cairou_{save/restore} with meta-synatax; specifically,
  something like: cairou_save(CAIROU_TRANSLATE, 1.0, 1.0, 1.0, CAIROU_SCALE, 1.0, 0.0).
