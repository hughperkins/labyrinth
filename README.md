Labyrinth
=========

## How does this compare to other forks of labyrinth?

* Uses a desktop load/save paradigm
  * when you open labyrinth, it will directly open the mind map editor window, with a new mind map
  * when you choose 'save', or press `ctrl-s`, it will ask you for a filepath, and then save the file
  * subsequent calls to 'save' or `ctrl-s` will save to the same filepath
  * when you exit, if any changes, asks if you want to save, asking for a filepath if none provided yet
  * you can provide a filepath on the commandline, when you start labyrinth
    * this file will then be opened in the mind map editor window
    * and any calls to 'save' or `ctrl-s` will save to this filepath
  * (cf the original fork is more like a mobile app, with its own internal database of mind maps, which you can export if you want)
* files are saved as xml files, rather than tars.  I'm not sure if this is good or bad, so feel free to raise an issue for this
  * good: better for use with `git`
  * bad: if you insert any images, I suppose they'll be lost???

## What is Labyrinth?

Labyrinth is a lightweight mind-mapping tool, written in Python using Gtk and
Cairo to do the drawing.  It is intended to be as light and intuitive as
possible, but still provide a wide range of powerful features.

A mind-map is a diagram used to represent words, ideas, tasks or other items
linked to and arranged radially around a central key word or idea. It is used
to generate, visualise, structure and classify ideas, and as an aid in study,
organisation, problem solving, and decision making. (From wikipedia)

Currently, Labyrinth provides 3 different types of thoughts, or nodes - Text,
Image and Drawing.  Text is the basic standard text node.  Images allow you to
insert and scale any supported image file (png, jpeg, svg).  Drawings are for
those times when you want to illustrate something, but don't want to fire up
a separate drawing program.  It allows you to quickly and easily sketch very
simple line diagrams.

License
-------

This software is released under the GNU GPL v2 (or later) license.  All source
files are included in this, unless explicitly stated in the source file itself.
For copyright owners, please refer to the source files individually.

The "labyrinth" icon (``data/labyrinth.svg`` and ``data/labyrinth-*.png``) is
copyright Josef Vybíral and is released under the GNU GPL v2 license.

Please refer to the "COPYING" file for a complete copy of the GNU GPL v2
license.

All documentation (This file, anything in the docs directory) released with
this package is released as public domain.  The documentation, you can do with
as you please.

Requirements
------------

* Python >= 2.6
* gtk+
* pygtk
* pygobject
* pycairo
* PyXDG

The minimum required versions are unknown, but any reasonably recent packages
should work.

How to use it
-------------

From the top directory of the package, run the command::

```
./labyrinth
```
... to open an empty mind map

or:
```
./labyrinth myfile.map
```
... to open an existing file `myfile.map`

In a new map, single click somewhere to create a new "thought".  This is your
root.  Add your main thought to this.  Click somewhere else will create a new
thought, linked to the first.  To move thoughts around, single-click and drag.
To edit a current thought, double click on it (text thoughts only).

Drawing and Image thoughts can be resized using their corners / sides.

Links between thoughts can be created, strengthened and weakened.  To create a
new link, in edit mode, click and drag from the "parent" thought to the "child"
thought while holding down the ctrl key.  Doing this with a link already in
place will strengthen the link by 1 and dragging from child to parent will
weaken the link by 1.  If the link goes to 0 strength (it starts at 2),
the link is deleted.  Links can also be created / deleted by selecting both
thoughts (hold down the shift key to select > 1 thought) and choosing
"Edit->(Un)Link Thoughts" from the menu (shortcut: Ctrl-L).

