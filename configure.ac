#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.68])
AC_INIT(faulty.lib, 0.0.1)
AC_CANONICAL_SYSTEM
AC_CONFIG_SRCDIR([linker/ElfLoader.h])
AC_CONFIG_HEADERS([config.h])
AC_PROG_CXX

case "$host" in
*-android*|*-linuxandroid*)
  AC_DEFINE([ANDROID], 1, Define to 1 when building for Android)
  LDFLAGS="${LDFLAGS} -llog"
  ;;
esac
LDFLAGS="${LDFLAGS} -ldl"
AC_CHECK_FUNCS([dladdr])
AC_CONFIG_FILES([linker/Makefile
                 tests/Makefile
                 mozilla/Makefile
                 Makefile
                 config/autoconf.mk])
AC_OUTPUT
sed -i 's,^DEPTH\t\t= ../..,DEPTH\t\t= ..,' linker/Makefile tests/Makefile mozilla/Makefile