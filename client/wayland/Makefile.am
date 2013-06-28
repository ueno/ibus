# vim:set noet ts=4:
#
# ibus - The Input Bus
#
# Copyright (c) 2007-2013 Peng Huang <shawn.p.huang@gmail.com>
# Copyright (c) 2007-2013 Red Hat, Inc.
#
# This library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation; either
# version 2 of the License, or (at your option) any later version.
#
# This library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public
# License along with this program; if not, write to the
# Free Software Foundation, Inc., 59 Temple Place, Suite 330,
# Boston, MA  02111-1307  USA


libibus = $(top_builddir)/src/libibus-@IBUS_API_VERSION@.la

libexec_PROGRAMS = ibus-wayland

ibus_wayland_SOURCES =				\
	main.c					\
	input-method-protocol.c			\
	input-method-client-protocol.h		\
	$(NULL)

ibus_wayland_DEPENDENCIES =			\
	$(libibus)				\
	$(NULL)

ibus_wayland_LDADD =				\
	$(libibus)				\
	$(GIO2_LIBS)				\
	$(WAYLAND_LIBS)				\
	$(NULL)

ibus_wayland_CFLAGS =				\
	$(GIO2_CFLAGS)				\
	$(WAYLAND_CFLAGS)			\
	-I$(top_srcdir)/src			\
	-I$(top_builddir)/src			\
	$(NULL)

$(libibus):
	(cd $(top_builddir)/src; make)

BUILT_SOURCES =					\
	input-method-protocol.c			\
	input-method-client-protocol.h		\
	$(NULL)

CLEANFILES = $(BUILT_SOURCES)

@wayland_scanner_rules@

-include $(top_srcdir)/git.mk
