# Readme #

license: My code is GPLv2

Current Version: svn-31 (17/May/2010)


**Requires**
ncurses library. You might get a ncurses.h not found. Install the libncurses5-dev library in debian/ubuntu ( **sudo apt-get install libncurses5-dev** ). Similar package should also exist in other linux distributions.


**Compiling:**
32/64-bit linux:
> make

**Running:**
> sudo ./i7z

> needs sudo, as MSR are usually only superuser readable/writeable. or if the device nodes
> are readable under your account then they will work out fine without the sudo

> need ncurses library: usually something like libncurses on debian.
also needs support of MSR (model specific register) in kernel. Usually most kernels
have it. Else run the MAKEDEV file. I do modprobing of msr within the C-program now so running the MAKEDEV file shouldnot be required

I added in new code that shows a nice GUI.
The Makefile for that is in GUI/ subdirectory. Just install a couple of qt packages
and you should be all set to run it. There is a README file that lists those packages


**Compiling:**
32/64-bit linux (in the GUI directory):
> make

**Running GUI:**
> sudo ./i7z\_GUI


Installation
> sudo make install

## Wishlist ##

command line options

## Version and Bug History: ##

**v svn-31 (17/May/2010)**
> Supports Dual sockets. Allows for on the fly disabling/enabling of cores without
> crashing.

**v0.21-4 (22/Feb/2010)**
> No bugs fixed, except better documentation of the code and fixing on the Makefiles,
> c/header files and better loading/checking of msr

**v0.21-3 (13/Feb/2010)**
> Minor Bug Fix, that happened as auto typecasting of double to float wasn't done
> A variable (numLogical) was getting overwritten, so moved it to global
> Seems that flags for optimization were screwing things up, so now no optimization
> GUI still has -O1 optimization flags

> BTW why sudden increase from 0.2-1 to 0.21-3. There were 3 minor edits in between
> And then for me 0.21 and 0.2 are just 0.01 apart rather then 19 minor aparts.
> I realised it too late and the svn was updated so many times that i'll keep it
> this way this time

**v0.21 (12/Feb/2010)**
> Lots of edits. Namely changed the way the number of cores were always fixed at 4
> Now arbitrary number of cores can be detected, thus i3, i5, i7 and gulftown (6-cores)
> can be detected. Also added code to detect the whole nehalem family rather than just i7

> Removed Intel\_CPUID directory which was used earlier to know the number of logical
> and physical processor. It was iffy when cores where shut down in OS and when license
> was concerned. Now i use just /proc/cpuinfo to figure out stuff.

**v0.2**

> added a gui version that uses qt4. makefile in GUI subdirectory
> now C0+C1+C3+C6 = 100%

**v0.1**

> simple i7 detection utility for overclockers and clockers :)

**v0.01**- very simple program to examine i7 feature clocking and running with speedstep
> Checked on 64-bit linux only. Should work on 32-bit too.

> need ncurses library: usually something like libncurses on debian.
> also needs support of MSR (model specific register) in kernel. Usually most kernels
> have it. Else run the MAKEDEV file. I do modprobing of msr within the C-program.





coder: Abhishek Jaiantilal (abhishek.jaiantilal@colorado.edu)