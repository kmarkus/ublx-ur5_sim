m4_define([package_version_major],[0])
m4_define([package_version_minor],[0])
m4_define([package_version_micro],[1])

AC_INIT([mypid], [package_version_major.package_version_minor.package_version_micro])
AM_INIT_AUTOMAKE([foreign -Wall])

# compilers
AC_PROG_CC

PKG_PROG_PKG_CONFIG
PKG_INSTALLDIR

AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])

# Check if the `install` program is present
AC_PROG_INSTALL

m4_ifdef([AM_PROG_AR], [AM_PROG_AR])
LT_INIT(disable-static)

PKG_CHECK_MODULES(UBX, ubx0 >= 0.9.0)

PKG_CHECK_VAR([UBX_MODDIR], [ubx0], [UBX_MODDIR])
  AC_MSG_CHECKING([ubx module directory])
  AS_IF([test "x$UBX_MODDIR" = "x"], [
  AC_MSG_FAILURE([Unable to identify ubx module path.])
])
AC_MSG_RESULT([$UBX_MODDIR])

AC_CONFIG_FILES([Makefile])
AC_OUTPUT

