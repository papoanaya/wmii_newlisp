;****** wmii_newlisp/README.md
;
; NAME 
;   README.md
; 
; SYNOPSIS 
;    Program documentation
;
;
; AUTHOR 
;    Luis R. Anaya
; 
; COPYRIGHT 
;    (c) 2012 by Luis R. Anaya
; 
; $RCSfile: events.nlsp $
; $Revision: 1.0 $
; $Date: $
; Author: $
;
; SOURCE
 
* Motivation
 
wmii_newlisp is a drop in replacement of the wmiirc files and shell scripts 
used by the wmii window manager (wmii.suckless.org)

It was written out of a necessity of having a lightweight implementation
of the shell based scripts using something "other than shell"
in a customer site. 

I usually have newlisp compiled almost everywhere I work in because of its 
small size and performance.  In this specific case, the shell script 
configuration in use in this site had a hard coded timeout value, causing
the window manager to stop working after a while. Developing
these in newlisp gave me a relatively simple way to have the
same functionality. 

* Installation 
TBD - After documenting the code.

;******
