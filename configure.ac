dnl -*- mode: m4 -*-
AC_PREREQ(2.63)
AC_INIT([gnome-font-viewer],[3.3.0],[],[gnome-font-viewer])

AC_CONFIG_HEADERS(config.h)
AC_CONFIG_MACRO_DIR([m4])

m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

AC_CANONICAL_TARGET

# require automake 1.10
AM_INIT_AUTOMAKE([1.10 dist-bzip2 no-dist-gzip foreign])
AM_MAINTAINER_MODE

GETTEXT_PACKAGE=AC_PACKAGE_NAME
AC_SUBST(GETTEXT_PACKAGE)
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE,"$GETTEXT_PACKAGE",[The name of the gettext domain])
IT_PROG_INTLTOOL(0.40.0)
PKG_PROG_PKG_CONFIG([0.22])

AM_GNU_GETTEXT([external])
AM_GNU_GETTEXT_VERSION([0.17])

## don't rerun to this point if we abort
AC_CACHE_SAVE

AC_PROG_CC
AM_PROG_CC_C_O
AC_PROG_CXX
AC_ISC_POSIX
AC_HEADER_STDC

AM_DISABLE_STATIC
# enable libtool
AC_PROG_LIBTOOL
# avoid libtool for LTCOMPILE, use it only to link

## don't rerun to this point if we abort
AC_CACHE_SAVE

GLIB_GSETTINGS

GLIB_MIN_VERSION=2.28.0
GTK_MIN_VERSION=3.0.0

PKG_CHECK_MODULES(FONTVIEW,
                  freetype2
                  gio-2.0 >= $GLIB_MIN_VERSION
                  glib-2.0 >= $GLIB_MIN_VERSION
                  gtk+-3.0 >= $GTK_MIN_VERSION)

AC_CONFIG_FILES([
Makefile
src/Makefile
src/gnome-font-viewer.desktop.in
po/Makefile.in
])

AC_OUTPUT

dnl ==========================================================================
echo "

        GNOME Font Viewer $VERSION
        ==========================

        prefix:    ${prefix}
        compiler:  ${CC}

        Now type 'make' to build $PACKAGE
"
