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
performance at the expense of memory consumption. This is a long term
objective. 

* Dmenu is being used rather than the default wmimenu. This is because 
of problems compiling wmimenu in Solaris and ARM.  In consequence
the colors are embedded in the code and not easily configurable. 


Bugs
----

Plenty... Get Real Kill or RAID to terminate. Brave souls could also
create an issue ticket in github. 

Installation 
------------
I took the easy way out for installation and works for me. 
In this case, your mileage may vary and depends on the amount
of desired user intervention.

If installing wmii from a packaged repository (apt, deb, pkg_man, etc)
it will install the shell version by default.  If compiling from source 
downlaoded from http://wmii.suckless.org, then the installation step 
will create those as well and store them in /etc. 

If you are *still* inclined to install and use the wmii_newlisp scripts
use the following steps that are not newbie friendly. (I apologize
for that, but suckless tools are catered for experienced UNIX users. I 
am following suit.). 

1. Install newlisp in a path accessible location (/usr/bin, /usr/local/bin)

2. Install dmenu in a path accessible location. (http://dwm.suckless.org)

3. Locate the directory where the wmii configuration is located, usually in 
/etc/wmii or in /etc/X11/wmii

4. Save a copy of the aforementioned wmii configuration directory.

5. Copy all the provided scripts by the wmii_newlisp package in the wmii 
configuration directory.

6. Make wmiirc executable by typing: chmod 755 wmiirc.

7.  Restart your window manager session and select to start wmii   This can be 
either by: Selecting wmii in your desktop manager or starting wmii directly 
after exiting from your running window manager.

8. Test. 

Ideally you should test by executing wmii against Xnest to ensure that the
handlers are working before using it for daily use. For additional 
documentation, go to http://wmii.suckless.org/. The documentation contains
a list of wmii key bindings and list of available functionalities.

License
-------
This code has been developed under the terms and conditions of the 
GNU Public License version 3.0 as described in the license file (LICENSE) 
included in the distribution.  Even though this software is harboring itself
under this license, it is in no part of the Gnu software offerings. 
