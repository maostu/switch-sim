#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([remy], [0.1], [anirudh@mit.edu])
AM_INIT_AUTOMAKE([foreign])
AC_CONFIG_SRCDIR([src/switch_sim.cc])
AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CXX
AC_PROG_RANLIB

# Add picky CXXFLAGS
CPPFLAGS="-std=c++11 -pthread"
PICKY_CXXFLAGS="-pedantic -Wconversion -Wall -Wextra -Weffc++ -Werror -fno-default-inline"
AC_SUBST([PICKY_CXXFLAGS])

# Checks for header files.
AC_LANG_PUSH(C++)

AC_CHECK_HEADERS([algorithm array cassert cmath queue \
cstdio string sys/stat.h sys/types.h ctime tuple unistd.h unordered_map \
utility vector], [], [AC_MSG_ERROR([Missing header file])])

AC_CHECK_LIB(jemalloc, malloc, [], [AC_MSG_ERROR([Need jemalloc])])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_TYPE_SIZE_T
AC_TYPE_UINT64_T
AC_LANG_POP(C++)

# Checks for library functions.

AC_CONFIG_FILES([Makefile src/Makefile])
AC_OUTPUT
