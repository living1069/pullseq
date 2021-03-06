#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([pullseq], [1.0.1], [bct.x42@gmail.com])
#AC_CONFIG_AUX_DIR(config)
AM_INIT_AUTOMAKE([foreign])
AC_CONFIG_SRCDIR([src/pullseq.c])
AC_CONFIG_HEADERS([src/config.h])

# Checks for programs.
AC_PROG_CC

# Checks for libraries.
AC_CHECK_LIB([z],[gzopen])
AC_CHECK_LIB([pcre],[pcre_compile], [], [
              echo "  Error! You need to have libpcre installed."
              echo "  If you have PCRE installed in a non-standard"
              echo "  location (e.g. as with brew on a mac), you'll"
              echo "  need to update the CFLAGS/LDFLAGS env"
              echo "  variables. See the README for more details."
              exit -1
              ])

# Checks for header files.
AC_CHECK_HEADERS([inttypes.h limits.h stddef.h stdlib.h string.h])
AC_CHECK_HEADERS([pcre.h], [], [
                  echo "  Error! You need to have libpcre installed."
                  echo "  If you have PCRE installed in a non-standard"
                  echo "  location (e.g. as with brew on a mac), you'll"
                  echo "  need to update the CFLAGS/LDFLAGS env"
                  echo "  variables. See the README for more details."
                  exit -1
                 ])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_INLINE
AC_TYPE_SIZE_T
AC_TYPE_SSIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT8_T
AC_CHECK_TYPES([ptrdiff_t])

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([strlen memset strchr strerror strtol])


AC_CONFIG_FILES([Makefile src/Makefile])

AC_OUTPUT

