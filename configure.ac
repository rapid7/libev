AC_INIT([libev], [4.24])

AC_CONFIG_SRCDIR([ev_epoll.c])

dnl also update ev.h!
AM_INIT_AUTOMAKE([subdir-objects foreign])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_HEADERS([config.h])
AM_MAINTAINER_MODE

AC_PROG_CC

AC_PROG_INSTALL
AC_PROG_LIBTOOL

AC_EGREP_CPP(we_are_using_clang,
[
#include <unistd.h>
#ifdef __clang__
we_are_using_clang
#endif
],
[AC_MSG_RESULT([yes])
IS_CLANG="yes"],
[AC_MSG_RESULT([no])])

if test x"$IS_CLANG" == x"yes" ; then
	CFLAGS="$CFLAGS -Wall -Wno-implicit-function-declaration -Wno-unused-value -Wno-unused-function"
fi

m4_include([m4/libev.m4])

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
