INCLUDES                 = -I$(top_srcdir)/ew

AM_LDFLAGS               = $(top_builddir)/ew/utils/libutils.la \
                           $(top_builddir)/ew/sed/libsedflux.la

bin_PROGRAMS             = avulsion
avulsion_SOURCES         = avulsion_main.c bmi_avulsion.c
avulsion_DEPENDENCIES    = libavulsion.la
avulsioninclude_HEADERS  = avulsion.h bmi_avulsion.h bmi.h
avulsionincludedir       = $(includedir)/ew-2.0

lib_LTLIBRARIES          = libavulsion.la
libavulsion_la_SOURCES   = avulsion.c avulsion_api.c

avulsion_LDADD           = -lavulsion -lglib-2.0

