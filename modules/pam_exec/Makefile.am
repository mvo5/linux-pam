#
# Copyright (c) 2006 Thorsten Kukuk <kukuk@suse.de>
#

CLEANFILES = *~

EXTRA_DIST = README $(MANS) $(XMLS)

man_MANS = pam_exec.8

XMLS = README.xml pam_exec.8.xml

securelibdir = $(SECUREDIR)
secureconfdir = $(SCONFIGDIR)

AM_CFLAGS = -I$(top_srcdir)/libpam/include -I$(top_srcdir)/libpamc/include
AM_LDFLAGS = -no-undefined -avoid-version -module \
	-L$(top_builddir)/libpam -lpam
if HAVE_VERSIONING
  AM_LDFLAGS += -Wl,--version-script=$(srcdir)/../modules.map
endif

securelib_LTLIBRARIES = pam_exec.la

if ENABLE_REGENERATE_MAN

noinst_DATA = README

README: pam_exec.8.xml

-include $(top_srcdir)/Make.xml.rules
endif
