#
#  This program is free software; you can redistribute it and/or modify
#  it under the terms of the GNU General Public License as published by
#  the Free Software Foundation; either version 2 of the License, or
#  (at your option) any later version.
#
#  This program is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#  GNU Library General Public License for more details.
#
#  You should have received a copy of the GNU General Public License
#  along with this program; if not, write to the Free Software
#  Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301,
#  USA.
#
#  MATE Livescore applet written by Assen Totin <assen.totin@gmail.com>
#

APPLET_FLAGS=@APPLET_FLAGS@
APPLET_LIBS=@APPLET_LIBS@
HAVE_MATE=@HAVE_MATE@

AM_CPPFLAGS = @GTK_CFLAGS@ @APPLET_FLAGS@
AM_LDFLAGS = -rdynamic
LDADD = @GTK_LIBS@ @APPLET_LIBS@ -ldl 

libexec_PROGRAMS = livescore_applet

livescore_applet_SOURCES = applet.h http.h util.c http.c fifo.c manager.c gui.c menu.c main.c 

appletdir = $(datadir)/mate-panel/applets
applet_DATA = org.mate.applets.LivescoreApplet.mate-panel-applet

servicedir = $(datadir)/dbus-1/services
service_DATA = org.mate.panel.applet.LivescoreApplet.service

gsettingsdir = $(datadir)/glib-2.0/schemas
gsettings_DATA = org.mate.panel.applet.LivescoreApplet.gschema.xml

serverdir = $(libdir)/bonobo/servers
server_DATA = LivescoreAppletFactory.server

install-data-hook:
	if test $(HAVE_MATE) = "1" ; then glib-compile-schemas $(DESTDIR)$(datadir)/glib-2.0/schemas 2>/dev/null; fi

