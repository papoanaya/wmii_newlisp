WMII_NEWLISP
===========
 
wmii_newlisp is a drop in replacement of the wmiirc files and shell scripts 
used by the wmii window manager (wmii.suckless.org)

Motivation
----------

It was written out of a necessity of having a lightweight implementation
of the shell based scripts using something "other than shell"
in a customer site. 

I compile newlisp almost everywhere I work in because of its 
small size and performance.  In this specific case, the shell script 
configuration in use in this particular site had a hard coded timeout value, 
causing the window manager to stop working after a while.  A solution
was needed being that I am an avid wmii user. 

Even though there are scripts for plan 9's rc, python and ruby available
in the stock installation of wmii,  none of these were suitable in this specific 
case because of lack of availability, dependencies  and footprint. 

Developing these in NewLisp gave me a relatively simple way to have the
same functionality in a small package. Even though it is a straight copy
from the shell scripts, it provides a foundation to expand these scripts
in a fast and flexible language.

Known Issues
------------

The following are known issues that will be addressed as time permits:

* Changed current macro implementation to a dictionary. This allows
for improved execution performance and the ability to add 
features without the need of a restart.

* Make sure that all processes terminate when quit hits. For the 
most part it has been addressed in the current version. But from 
time to time, a process keeps dangling around. There is code
to check for process but it may be a bit expensive to run for
every transaction. A solution is being researched. 

* Move from the shell implementation to direct libixp calls. Should improve
performance at the expense of memory consumptions. This is a long term
objective. 

* Dmenu is being used rather than the default wmimenu. This is because 
of problems compiling wmimenu in Solaris and ARM.  In consequence
the colors are embedded in the code and not easily configurable. 


Installation 
------------
TBD - After documenting the code.

License
-------
This code has been developed under the terms and conditions of the 
GNU Public License version 3.0 as described in the license file (LICENSE) 
included in the distribution.  Even though this software is harboring itself
under this license, it is in no part of the Gnu family of software offerings. 
