


                                 ------------
                                    Poedit
                                 ------------
                                  
              a cross-platform Gettext catalogs editing tool


 About
=======

This program is GUI frontend to GNU Gettext utilities (win32 version
is part of the distribution) and catalogs editor/source code parser. It helps
with translating application into another language. For details on principles
of the solution used, see GNU Gettext documentation or wxWidgets' wxLocale 
class reference.


 Installing
============

Binary easily-installable packages are provided for Windows and OS X and are
part of many Linux distributions.


 Installing from sources
=========================

Poedit is built on top of wxWidgets toolkit, so it requires it at compilation
time (version 2.8.0 or newer, in Unicode build, see http://www.wxwidgets.org).
Additional requirements are Berkeley DB >= 3 if you need translation memory and
GtkSpell 2.x plus GTK+ 2 build of wxWidgets for spell checking support (Unix
only).

Unix and OS X/Windows using GNU toolchain
-----------------------------------------

Do the usual thing:
    ./configure
    make
    make install
This works on OS X (which is a standard BSD Unix system) and Windows with
MinGW toolchain and MSYS shell installed. You must have the dependencies
installed in a location configure will find, e.g. by setting CPPFLAGS and
LDFLAGS appropriately.

Win32 version is distributed as precompiled binary with Gettext utilities
included. You don't need wxWidgets for it. If you want to compile Poedit
yourself, then the best way is to install Mingw and MSYS and use Unix
way of building the library.

OS X
----

After compiling the application as above, you can additionally create an OS X
bundle by running "make bundle" in the src/ subdirectory. This requires that
GETTEXT_PREFIX environment variable is set and points to a directory with
compiled GNU Gettext programs installed (e.g. msgfmt; GETTEXT_PREFIX=/opt/local
works if you used MacPorts to install Gettext and so msgfmt is in
/opt/local/bin/msgfmt). Finally, running "make dist-osx" in the toplevel
directory will create disk image with the bundle.

Windows using Visual Studio 2005 Express
----------------------------------------

Visual Studio makefile is in win32/ directory. Change to this directory
and run "nmake -f makefile.vc [additional options]". The flags to set are
documented near the top of the makefile. In particular, you have to set the
WX_DIR variable to point to wxWidgets installation (by default, WXWIN
environment variable is used), WXRC variable to point to wxWidget's wxrc.exe,
point DB_PATH to Berkeley DB tree with compiled static library and set
DB_VERSION to the version you use, if it differs from the setting in the
makefile.

Once the program is compiled, you may wish to create the installer. Inno Setup
is used for installation on Windows and it's made to use the VS2005 binaries.
In order to compile the installer, you must first copy Gettext binaries to
deps/gettext directory - if you don't, the installer will report errors.


 License
=========

Poedit is released under the MIT license and you're free to do 
whatever you want with it and its source code (well, almost :-) -- see the
license text).

Icons are from the Tango Desktop Project [http://tango.freedesktop.org]
and Mark James's Silk icons set [http://www.famfamfam.com/lab/icons/silk].

See the COPYING file for details on program's licensing and the
src/icons/README file for details on the icons.

Win32 and Mac OS X versions contain GNU Gettext binaries. They are distributed
under the GNU General Public License and their source code is available from
http://www.gnu.org/software/gettext or, if you have difficulties getting them
from there, email me for a copy of the sources.


 Author
========
 
Vaclav Slavik <vslavik@fastmail.fm>
Please see the AUTHORS file for information about other contributors.


 Links
=======

http://www.poedit.net
        - Poedit homepage

http://www.wxwidgets.org
        - wxWidgets toolkit homepage
http://www.gnu.org
        - GNU project homepage, contains Gettext and documentation
http://www.innosetup.org
http://isx.wintax.nl
        - Inno Setup and Inno Setup Extensions, installation
          program used by Poedit under Windows
