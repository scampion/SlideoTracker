.. SlideoTracker documentation master file, created by
   sphinx-quickstart on Fri Feb 11 14:12:24 2011.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Introduction
============
Based on computer vision algorithms, this software enables to synchronize slides with the corresponding video recording.

.. note:: slideotracker = slides + video + tracking

* Author : Sebastien Campion / INRIA Texmex Team / http://www.irisa.fr/texmex

Licence
=======
GNU AFFERO GENERAL PUBLIC LICENSE v3

Screencast
==========

.. raw:: html

  <iframe title="YouTube video player" width="640" height="390" src="http://www.youtube.com/embed/74yZJ63h-Ow" frameborder="0" allowfullscreen></iframe>


Download
========

Debian package
--------------

make deb


Python packages 
-------------

make pydist


Source code
-----------

https://github.com/scampion/slideotracker


Usage
=====

.. 

  Usage: slideotracker.py [options] [slides]

  Parameters:
  sli  des              paths to slide images (use ImageMagick, to
                        convert pdf into several images)

  Options:
  -h, --help            show this help message and exit
  -v video, --video=index
                        video path
  -p PRECISION, --precision=PRECISION
                        precision in number of frame (default 25)
  -o OUTFILE, --out=OUTFILE
                        output file name, by default results.js
  -f FORMAT, --format=FORMAT
                        output file format js (default),csv
  -d, --debug           debug trace


Example 
-------

Real test
_________

Download and extract : 
  http://slideotracker.gforge.inria.fr/demo/demo.tar.gz
  
Run ::

  slideo -i test/data/video.avi tests/data/slide*.jpg


Common use
__________

.. code-block:: bash

  #extract pdf pages to jpeg using ImageMagick
  mkdir /tmp/mypdf/
  convert <your.pdf> /tmp/mypdf/slide.jpg
  #Run the tracker  
  python slideotracker.py -v ./path/to/my/video.ogv -o results.txt /tmp/mypdf/slide*

try also :
  python slideotracker.py -i tests/data/short_test.txt

Results in Javascript format :

slides=[0, 1, 2];

frames=[500, 850, 950];
 

Results in CSV format :

#slide_number;star_frame;end_frame

0;0;500

1;500;850

2;850;950

...
..
.

Display results in HTML5
========================
Open the following file with your browser ::

/usr/share/slideo/html/player.html?mediafile=data/video.ogv&slidedir=data/slides&fps=25

Dependencies
============

  * scikit-learn 
  * OpenCV 2.1 

TODO/Roadmap
============

  * geometric robustification ... in progress
  * optimize time computing
  * documentation / How it works 

Credits
=======
  * Images used for the logo : Dropline Nuovo! from http://art.gnome.org/themes/icon
  * RMLL 2010 video for the data test

 

