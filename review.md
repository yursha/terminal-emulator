# Review of terminal emulators

A terminal emulator allows a user to interact with a shell from within a GUI environment (Xorg or Wayland).

LOC metric was obtained with the following command (text files only):

```
sh> find . -type f -exec grep -Iq . {} \; -and -print0 | xargs -0 wc -l
```

Programming language breakdown was obtained with [`github-linguist`](https://github.com/github/linguist).

Size with all dependencies, excluding `glibc`:

- xterm - 167 MiB
- kitty - 221 MiB (but doesn't mention `python` which is +321 MiB)
- rxvt-unicode - 240 MiB
- qterminal - 467 MiB
- liri-terminal - 503 MiB
- gtk3 - 718 MiB (vte3, moserial, termite, 
- vte3 - 719 MiB (gnome-terminal, mate-terminal, lxterminal, guake, pantheon-terminal, xfce4-terminal, terminator, sakura, tilda, tilix)
- terminology - 854 MiB
- konsole - 888 MiB (yakuake)

## st

- LOC: 6707
- implementation languages: C (80%), Objective-C (15%), Roff (3%), Makefile (2%)

## kitty

- LOC: 179,166
- implementation languages: C (46%), Python (43%), Objective-C (9%), Mathematica (1%)

## xterm, uxterm

A vt220 terminal emulator. The standard terminal emulator for the X Window System.

http://invisible-island.net/xterm/

- website: 
- first release: , last release: 
- sources: 
- version control: 
- LOC: 174,973
- dependencies:
    + libutempter
    + libxaw
    + libxft
    + libxkbfile
    + ncurses
    + xbitmaps
    + xorg-luit
- implementation languages: C (68%), HTML (15%), Roff (11%), Perl (2%)
- features:

## xvt

X Window System terminal emulator.

http://www.rpi.edu/dept/acm/www/packages/xvt-1.0.html

Xvt is a VT100 terminal emulator for X.
It is intended as a replacement for `xterm(1)` for users who do not require the more esoteric features of xterm.
Specifically xvt does not implement the Tektronix 4014 emulation, session logging and [xt](https://en.wikipedia.org/wiki/X_Toolkit_Intrinsics)-style configurability.
As a result, xvt uses much less memory.
`xvt` options are mostly a subset of `xterm`.

## rxvt

A fork of xvt.

rxvt (acronym for *our extended virtual terminal*)

- website: http://rxvt.sourceforge.net/
- first release: 2000, last release: 2001
- LOC: 80,140
- implementation languages: C (78%), Shell (17%), Makefile (3%)

## rxvt-unicode (a.k.a. urxvt)

A fork of rxvt.

Unlike the original `rxvt`, `rxvt-unicode` stores all text in Unicode internally. `rxvt-unicode` was born was solely because the author couldn't get `mlterm` to use one font for latin1 and another for japanese. 

- website: http://software.schmorp.de/pkg/rxvt-unicode.html
- first release: 2003, last release: 2016
- sources: http://cvs.schmorp.de/rxvt-unicode/
- version control: CVS
- LOC: 115,413
- dependencies:
    + libnsl
    + libxft
    + perl
    + rxvt-unicode-terminfo
    + startup-notification
    + gtk2-perl (optional) - to use the urxvt-tabbed
- implementation languages: C (89%), Perl (4%), C++ (4%)
- features:
  + ISO/IEC 14755
  + separate font per script
  + support for X FreeType interface library (XFT)
  + comes with a client/daemon pair (urxvtd(1) and urxvtc(1)) that lets you open any number of terminal windows from within a single process, which makes startup time very fast and drastically reduces memory usage.

## gnome-terminal

- dependencies:


# Supporting libraries

## X FreeType interface library (xft)

https://freedesktop.org/wiki/Software/Xft/

It is designed to allow the FreeType rasterizer to be used with the X Rendering Extension; it is generally employed to use FreeType's anti-aliased fonts with the X Window System. Xft also depends on `fontconfig` for access to the system fonts.

## VTE

https://github.com/GNOME/vte

- first release: 2002, last release: 2018
- sources: https://github.com/GNOME/vte
- LOC: 87,651
- dependencies:
    + gnutls
    + gtk3
    + pcre2
    + vte-common
    + git (make)
    + glade (make)
    + gobject-introspection (make)
    + gperf (make)
    + gtk-doc (make)
    + intltool (make)
    + vala (make)
- implementation languages: C++ (83%), C (10%), M4 (2%), Vala (1%)


