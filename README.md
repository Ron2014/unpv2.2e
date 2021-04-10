# unpv2.2e

CAVEATS
=======

1. Please do NOT send me email with your "make" output, asking me what to
   do to get the source code working on your system.  You would not believe
   the volume of email that I get like this, and I just don't have the
   time to even respond to these any more.  My suggestion is to get someone
   locally to help (at work or at school) or to ask on some vendor-specific
   Usenet newsgroup.

   My publisher graciously allows all the code to be made available (to save
   you from having to type it in), but the code is provided "as is" with no
   support implied.

2. The code in the book uses features that are not widespread during 1998
   (e.g., Posix IPC, a *working* pthreads library, Posix realtime signals,
   etc.).  The *only* Unix systems that I found that supported everything
   that I wanted to cover in the book were Solaris 2.6 and Digital Unix
   4.0B (excluding doors, which I know are Solaris-only, and Posix read-write
   locks, which only AIX supports).  If you are bringing up the source code
   on some other system *expect* to find features described in the book
   that your system does not support.

   I have brought up pieces of the code (mainly the library and a few
   test programs) on BSD/OS 3.1, RedHat Linux 5.1, and AIX 4.3.1, but I
   do not have the time and resources to try and port the code to all
   other possible Unix variants (and all the various Linux variants with
   different kernels and libraries).  I think the code is quite portable
   but it will require some effort to port the code to other Unix systems.

QUICK AND DIRTY
===============

Execute the following from the src/ directory:

    ./configure    # try to figure out all implementation differences

    cd lib         # build the basic library that all programs need
    make           # use "gmake" everywhere on BSD/OS systems

    cd ../pipe     # build and test a simple program
    make pipeconf
    ./pipeconf /tmp

If all that works, you're all set to start compiling individual programs.

Notice that all the source code assumes tabs every 4 columns, not 8.

MORE DETAILS
============
