AC_PREREQ(2.53)
AC_INIT([matchbox-common], 0.9, [mallum@handhelds.org])
AC_CONFIG_SRCDIR([icons/mbadd.xpm])

AM_INIT_AUTOMAKE()
AM_MAINTAINER_MODE
AM_CONFIG_HEADER([config.h])

# Checks for programs.

# XXX
# should be installed after libmb so we can check for;
#  - PNG support for png icons
#  
# XXX should install panel icons ?
#  --disable-panel-icons
#  

dnl ----- Args -------------------------------------------------------------


AC_ARG_ENABLE(pda_folders,
  [  --enable-pda-folders  Use PDA style app folder setup ( Rather than Desktop )],
     enable_pda_folders=$enableval, enable_pda_folders=no)

## AC_ARG_ENABLE(small-icons,
##  [  --enable-small-icons      Enable small defualt icons.],
##       enable_sicons=$enableval, enable_sicons=no)


dnl ---- Check for libmb so we can figure out PNG / XPM support ------------

PKG_CHECK_MODULES(LIBMB, libmb >= 1.1,, AC_MSG_ERROR([*** libmb required and not found ***]))

# below is quite bad ...
if $PKG_CONFIG --libs libmb | grep png ; then
   found_png="yes"
else
   found_png="no"	
fi

AM_CONDITIONAL(WANT_PNG, test x$found_png = xyes)  

## AM_CONDITIONAL(WANT_SMALL_ICONS, test x$enable_sicons = xyes)  

AM_CONDITIONAL(WANT_PDA_FOLDERS, test x$enable_pda_folders = xyes)  

## XXX should we install a .pc file so the panel and desktop can 
##     can check common has been installed ?

## panel should have a --enable-large-default-icons switch 
##      or summin 

## XXX add mbsession to this aswell

AC_OUTPUT([
Makefile
data/Makefile
data/vfolders-pda/Makefile
data/vfolders-desktop/Makefile
icons/Makefile
])

dnl ==========================================================================
echo "
                    matchbox-common $VERSION
                  ==========================

        prefix:                 ${prefix}
        source code location:   ${srcdir}

	Installing PNGs         ${found_png}
	Installing PDA Folders  ${enable_pda_folders}
"
